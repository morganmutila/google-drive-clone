<script setup>
import { Link } from '@inertiajs/vue3';
import ApplicationLogo from '../ApplicationLogo.vue';
import CreateNewDropdown from './CreateNewDropdown.vue';
import NavLink from '@/Components/NavLink.vue';
import { StarIcon, TrashIcon, UsersIcon, AtSymbolIcon, RectangleStackIcon } from '@heroicons/vue/20/solid';

</script>

<template>
    <nav class="min-w-[200px]">
        <div class="h-[80px] mx-3 px-3 flex items-center gap-3">
            <Link href="/">
                <ApplicationLogo
                 class="block h-9 w-auto fill-current text-gray-800"/>
            </Link>
            Google Drive Clone
        </div>

        <div class="mx-3 mb-4">
            <CreateNewDropdown />
        </div>

        <div class="py-3 mx-3">
            <NavLink
                :href="route('dashboard')"
                :active="route().current('dashboard')"
            >

            <RectangleStackIcon class="h-5 w-5 text-gray-700 mr-1 flex" />

                My files
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
            <UsersIcon class="h-5 w-5 text-gray-700 mr-1 flex" />

                Shared with me
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >

            <AtSymbolIcon class="h-5 w-5 text-gray-700 mr-1 flex" />

                Shared by me
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
            <StarIcon class="h-5 w-5 text-gray-700 mr-1 flex" />

                Starred
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
            <TrashIcon class="h-5 w-5 text-gray-700 mr-1 flex" />

                Trash
            </NavLink>
        </div>
    </nav>
</template>
