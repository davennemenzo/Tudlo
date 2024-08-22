<script setup>
import Button from "@/Components/Button.vue";
import Navbar from "@/Layouts/Navbar.vue";
import { useForm } from "@inertiajs/vue3";

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
});

const submit = () => {
    form.post(route("signup"), {
        onError: () => {
            form.reset("password", "password_confirmation");
        },
    });
};
</script>

<template>
    <Navbar></Navbar>

    <v-card class="mx-auto" max-width="344" hover>
        <v-card-item>
            <v-card-title> Signup </v-card-title>
            <v-form @submit.prevent="submit">
                <v-text-field
                    v-model="form.name"
                    label="Name"
                    outlined
                    dense
                    class="mb-3"
                    :error-messages="form.errors.name"
                >
                </v-text-field>
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

                <v-text-field
                    v-model="form.password_confirmation"
                    variant="outlined"

                    label="Password"
                    type="password"
                    class="mb-3"
                ></v-text-field>

                <p class="text-center mb-2">
                    Already have an account?
                    <a :href="route('login')" class="text-teal-accent-4"
                        >Log in</a
                    >
                </p>



                <Button
                type="submit"
                :disabled="form.processing"
                label="Submit"
                class="me-4 w-full py-4 pb-8 h-3 "
                
                >Submit</Button>
            </v-form>
        </v-card-item>
    </v-card>
</template>
