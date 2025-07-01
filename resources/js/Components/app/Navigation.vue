<script setup>
import { Link } from '@inertiajs/vue3';
import ApplicationLogo from '../ApplicationLogo.vue';
import CreateNewDropdown from './CreateNewDropdown.vue';
import NavLink from '@/Components/NavLink.vue';

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

        <div class="px-3 mx-3">
            <CreateNewDropdown />
        </div>

        <div class="py-3 mx-3">
            <NavLink
                :href="route('dashboard')"
                :active="route().current('dashboard')"
            >
                My files
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
                Shared with me
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
                Shared by me
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
                Starred
            </NavLink>

            <NavLink
                :href="route('dashboard')"
            >
                Trash
            </NavLink>
        </div>
    </nav>
</template>
