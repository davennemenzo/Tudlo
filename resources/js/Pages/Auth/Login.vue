<script setup>
import Navbar from "@/Layouts/Navbar.vue";
import { useForm } from "@inertiajs/vue3";

const form = useForm({
    email: null,
    password: null,
});

const submit = () => {
    form.post(route("login"), {
        onError: () => {
            form.reset("password");
        },
    });
};
</script>

<template>
    <v-card class="mx-auto" max-width="344" hover>
        <v-card-item>
            <v-card-title> Login </v-card-title>

            <v-form @submit.prevent="submit">
                <v-text-field
                    v-model="form.email"
                    label="Email"
                    outlined
                    dense
                    class="mb-3"
                    :error-messages="form.errors.email"
                ></v-text-field>

                <v-text-field
                    v-model="form.password"
                    label="Password"
                    outlined
                    dense
                    type="password"
                    class="mb-3"
                    :error-messages="form.errors.password"
                ></v-text-field>

                <div class="mb-4 ">
                  <input
                        type="checkbox"
                        v-model="form.remember"
                        id="remember"
                        class="border border-black"
                    />
                    <label class="ml-3" for="remember">Remember me</label>
                    
                </div>

                <p class="text-center mb-4">
                    Need an Account?
                    <a :href="route('signup')" class="text-teal-accent-4"
                        >Register</a
                    >
                </p>

                <v-btn
                    class="w-full py-4 pb-8 hover:opacity-80 bg-teal-lighten-1 text-center"
                    type="submit"
                    :disabled="form.processing"
                >
                    Login
                </v-btn>
            </v-form>
        </v-card-item>
    </v-card>
</template>
