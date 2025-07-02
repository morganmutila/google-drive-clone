<script setup>
import Navigation from '@/Components/app/Navigation.vue';
import SearchForm from '@/Components/app/SearchForm.vue';
import UserSettingsDropdown from '@/Components/app/UserSettingsDropdown.vue';


</script>

<template>
    <div class="h-screen flex gap-4 bg-gray-50 w-full">

        <Navigation/>

        <main class="flex flex-1 flex-col px-4 overflow-hidden">
            <div class="h-[80px] flex w-full items-center justify-between">
                <SearchForm />
                <UserSettingsDropdown/>
            </div>

            <div class="flex flex-col flex-1 overflow-hidden bg-white rounded-2xl
">
                <slot />

            </div>
        </main>

    </div>
</template>
