
<script setup>
import {Head, Link } from '@inertiajs/vue3';
    defineProps({
        canLogin: {
            type: Boolean,
        },
        canRegister: {
            type: Boolean,
        },
    });
</script>

<template>

    <Head>
        <title>Store and access your files anywhere</title>
        <meta name="description" content="A google drive clone">
    </Head>

    <div class="bg-gray-50 text-gray-800 min-h-screen">

        <!-- Header -->
        <header class="flex justify-between items-center px-6 py-4 shadow-md bg-white">
        <div class="text-2xl font-bold text-blue-600">DriveClone</div>
        <nav class="space-x-6">
            <Link href="#features" class="hover:text-blue-600">Features</Link>
            <Link href="#pricing" class="hover:text-blue-600">Pricing</Link>
            <div v-if="canLogin" class="inline-flex flex-1 justify-end">
                <Link
                    v-if="$page.props.auth.user"
                    :href="route('dashboard')"
                    class="hover:text-blue-600"
                    >
                        Dashboard
                </Link>
                <div v-else class="space-x-6">
                    <Link :href="route('login')" class="hover:text-blue-600">Login</Link>
                    <Link :href="route('register')" class="bg-blue-600 text-white px-4 py-2 rounded-xl hover:bg-blue-700">Sign Up</Link>
                </div>
            </div>
        </nav>
        </header>

        <!-- Hero -->
        <section class="flex flex-col md:flex-row items-center px-6 md:px-20 py-20 bg-gradient-to-r from-blue-50 to-white">
        <div class="flex-1 text-center md:text-left">
            <h1 class="text-4xl md:text-5xl font-extrabold mb-6 leading-tight">
            Store and access your files <br /> anytime, anywhere.
            </h1>
            <p class="text-lg text-gray-600 mb-6">
            Your personal cloud storage — secure, fast and easy to use. Backup, share and manage your files seamlessly.
            </p>
            <Link href="/register" class="bg-blue-600 text-white px-6 py-3 rounded-xl hover:bg-blue-700 text-lg">
            Get Started for Free
            </Link>
        </div>
        <div class="flex-1 mt-12 md:mt-0">
            <img src="https://www.gstatic.com/images/branding/product/2x/drive_2020q4_48dp.png" alt="Drive illustration" class="w-full max-w-md mx-auto" />
        </div>
        </section>

        <!-- Features -->
        <section id="features" class="py-16 bg-white px-6 md:px-20">
        <h2 class="text-3xl font-bold text-center mb-12">Why DriveClone?</h2>
        <div class="grid md:grid-cols-3 gap-10">
            <div class="text-center">
            <div class="text-blue-600 text-5xl mb-4">📁</div>
            <h3 class="text-xl font-semibold mb-2">Unlimited Storage</h3>
            <p class="text-gray-600">Upload and organize your files without limits — everything in one place.</p>
            </div>
            <div class="text-center">
            <div class="text-blue-600 text-5xl mb-4">🔒</div>
            <h3 class="text-xl font-semibold mb-2">Secure by Design</h3>
            <p class="text-gray-600">We use encryption and access control to keep your files safe.</p>
            </div>
            <div class="text-center">
            <div class="text-blue-600 text-5xl mb-4">🤝</div>
            <h3 class="text-xl font-semibold mb-2">Easy Collaboration</h3>
            <p class="text-gray-600">Share files with anyone and collaborate in real-time.</p>
            </div>
        </div>
        </section>

        <!-- CTA -->
        <section class="bg-blue-600 text-white py-16 text-center px-6">
        <h2 class="text-3xl font-bold mb-4">Ready to take control of your files?</h2>
        <p class="text-lg mb-6">Sign up today and start using DriveClone for free.</p>
        <Link href="/register" class="bg-white text-blue-600 px-6 py-3 rounded-xl text-lg font-semibold hover:bg-gray-100">
            Sign Up Free
        </Link>
        </section>

        <!-- Footer -->
        <footer class="text-center text-sm py-6 text-gray-500">
        &copy; {{ new Date().getFullYear() }} DriveClone. All rights reserved.
        </footer>

    </div>
</template>
