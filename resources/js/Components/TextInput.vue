<script setup>
    defineProps({
        name: {
            type: String,
            required: true,
        },
        type: {
            type: String,
            default: 'text',
        },
    })
</script>

<template>
    <div>
        <v-text-field
                    v-model="form.name"
                    label="name"
                    outlined
                    dense
                    class="mb-3"
                    :error-messages="form.errors.name"
                >
                </v-text-field>
    </div>
</template>