<template>
    <TransitionRoot as="template" :show="isOpen">
      <Dialog class="relative z-10" @close="closeModal">
        <div class="fixed inset-0" />
  
        <div class="fixed inset-0 overflow-hidden">
          <div class="absolute inset-0 overflow-hidden">
            <div class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full pl-10">
              <TransitionChild as="template" enter="transform transition ease-in-out duration-500 sm:duration-700" enter-from="translate-x-full" enter-to="translate-x-0" leave="transform transition ease-in-out duration-500 sm:duration-700" leave-from="translate-x-0" leave-to="translate-x-full">
                <DialogPanel class="pointer-events-auto w-screen max-w-md">
                  <div class="flex h-full flex-col divide-y divide-gray-200 bg-white shadow-xl">
                    <div class="flex min-h-0 flex-1 flex-col overflow-y-scroll py-6">
                      <div class="px-4 sm:px-6">
                        <div class="flex items-start justify-between">
                          <DialogTitle class="text-base font-semibold text-gray-900">Adicionar time</DialogTitle>
                          <div class="ml-3 flex h-7 items-center">
                            <button type="button" class="relative rounded-md bg-white text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500" @click="closeModal">
                              <span class="absolute -inset-2.5" />
                              <span class="sr-only">Close panel</span>
                              <XMarkIcon class="size-6" aria-hidden="true" />
                            </button>
                          </div>
                        </div>
                      </div>
                      <div class="relative mt-6 flex-1 px-4 sm:px-6">
                        <div>
                          <label class="block text-sm font-medium text-gray-700">Nome do Time</label>
                          <input v-model="teamName" class="mt-1 block w-full border rounded-md shadow-sm p-2">
                        </div>
                        <div>
                          <label class="block text-sm font-medium text-gray-700">Nome do Manager</label>
                          <input v-model="managerName" class="mt-1 block w-full border rounded-md shadow-sm p-2">
                        </div>
                      </div>
                    </div>
                    <div class="flex shrink-0 justify-end px-4 py-4">
                      <button type="button" @click="closeModal" class="rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:ring-gray-400">Cancel</button>
                      <button type="button" @click="saveTeam" class="ml-4 inline-flex justify-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500">Save</button>
                    </div>
                  </div>
                </DialogPanel>
              </TransitionChild>
            </div>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
  </template>
  
  <script>
  import {
    Dialog, DialogPanel, DialogTitle,
    TransitionChild, TransitionRoot
  } from '@headlessui/vue'
  import { XMarkIcon } from '@heroicons/vue/24/outline'
  export default {
    components: {
      Dialog, DialogPanel, DialogTitle,
      TransitionChild, TransitionRoot,
      XMarkIcon
    },
    props: {
      isOpen: Boolean,
    },
    data() {
      return {
        teamName: '',
        managerName: '',
      };
    },
    watch: { isOpen(val) { this.localIsOpen = val; } },
    methods: {
      saveTeam() {
        this.$emit('save', { name: this.teamName, manager: this.managerName });
        this.closeModal();
      }, closeModal() {
        this.localIsOpen = false; this.$emit('update:isOpen', false);
        }
      },
    }
    </script>
  
  