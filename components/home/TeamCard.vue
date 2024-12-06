<template>
  <div>
    <ul role="list" class="">
      <li class="col-span-1 flex rounded-md shadow-sm">
        <div class="border-l border-t border-b rounded-l-md ">
          <img class="w-12 h-12 m-1 rounded-full "
            src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60"
            alt="" />
        </div>
        <div
          class="flex flex-1 items-center justify-between rounded-r-md border-b border-r border-t border-gray-200 bg-white">
          <div class="flex-1 truncate px-4 py-2 text-sm">
            <a class="font-medium text-gray-900 hover:text-gray-600">{{ teamName }}</a>
            <p class="text-gray-500">{{ 'Manager: ' + managerName }}</p>
          </div>
          <div class="shrink-0 pr-2">
            <button type="button"
              class="inline-flex size-8 items-center justify-center rounded-full bg-transparent bg-white text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
              <span class="sr-only">Open options</span>
              <EllipsisVerticalIcon class="size-5" aria-hidden="true" />
            </button>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
  <script>
  import { EllipsisVerticalIcon } from '@heroicons/vue/20/solid'
  export default {
    components:{
      EllipsisVerticalIcon
    },
    props: {
      teamLogo: String,
      teamName: String,
      managerName: String,
    },
  }
  </script>
