<script setup lang="ts">
import { Link } from "@inertiajs/vue3";
</script>

<sciprt setup>
</sciprt>

<template>
    <nav class="bg-white border-b border-gray-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex-shrink-0 flex items-center">
                    <a href="#" class="text-4xl font-semibold">Tudlo</a>
                </div>
                <div class="hidden md:flex md:space-x-8 md:items-center">
                    <Link
                        :href="route('about')"
                        class="text-black hover:text-gray-600 font-bold"
                        >About</Link
                    >
                    <Link
                        :href="route('services')"
                        class="text-black hover:text-gray-600 font-bold"
                        >Services</Link
                    >

                    <a href="#" class="text-black hover:text-gray-600 font-bold"
                        >Become a Tutor</a
                    >
                </div>

                <div class="hidden md:flex md:space-x-3 md:items-center">

                    <Link :href="route('signup')" class="text-black hover:text-gray-600 font-bold">Signup</Link>


                    <Link :href="route('login')"
                        ><button
                            class="bg-blue-500 text-white hover:bg-blue-600 font-bold py-2 px-5 rounded"
                        >
                            Login
                        </button></Link
                    >
                </div>
            </div>
        </div>
    </nav>
</template>
