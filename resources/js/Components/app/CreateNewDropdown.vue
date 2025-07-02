
<script setup>
    import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue'
    import { FolderIcon, DocumentArrowUpIcon, PlusIcon } from '@heroicons/vue/20/solid'
</script>

<template>
    <Menu as="div" class="relative">
        <MenuButton
          class="flex w-full items-center bg-white justify-center shadow-md p-3 rounded-xl text-left">
          <PlusIcon class="w-6 h-6 mr-2 text-gray-600"/>
          New
        </MenuButton>

      <transition
        enter-active-class="transition duration-100 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <MenuItems
          class="absolute left-0 mt-1 w-56 origin-top-right divide-y divide-gray-100 rounded-md bg-white shadow-lg ring-1 ring-black/5 focus:outline-none"
        >
          <div class="px-1 py-1">
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                <DocumentArrowUpIcon class="h-5 w-5 mr-2 text-gray-400" />
                File upload
              </button>
            </MenuItem>

            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                <FolderIcon class="h-5 w-5 mr-2 text-gray-400" />

                Folder upload
              </button>
            </MenuItem>
          </div>
        </MenuItems>
      </transition>
    </Menu>
</template>
