<template>
  <div class="w-56 text-right">
    <Menu as="div" class="relative inline-block text-right">
      <div>
        <MenuButton
          class="inline-flex w-full justify-center">
          <UserCircleIcon class="w-10 h-10 text-gray-600"/>
        </MenuButton>
      </div>

      <transition
        enter-active-class="transition duration-100 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <MenuItems
          class="absolute right-0 mt-2 w-56 origin-top-right divide-y divide-gray-100 rounded-md bg-white shadow-lg ring-1 ring-black/5 focus:outline-none"
        >
          <div class="px-1 py-1">
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                Edit
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                Duplicate
              </button>
            </MenuItem>
          </div>
          <div class="px-1 py-1">
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                Archive
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                Move
              </button>
            </MenuItem>
          </div>

          <div class="px-1 py-1">
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-indigo-100 text-gray-900' : 'text-gray-900',
                  'group flex w-full items-center rounded-md px-2 py-2',
                ]"
              >
                Delete
              </button>
            </MenuItem>
          </div>
        </MenuItems>
      </transition>
    </Menu>
  </div>
</template>

<script setup>
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue'
import { ChevronDownIcon, UserCircleIcon } from '@heroicons/vue/20/solid'
</script>
