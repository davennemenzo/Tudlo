<script setup>
    const props = defineProps({
        inputName: {
            type: String,
            default: 'name',
        },
        inputType: {
            type: String,
            default: 'text',
        },
    })
</script>

<template>
    <div>
        <v-text-field

                    :label="props.inputName"
                    :type="props.inputType"
                    v-model="form.name"
                >
                </v-text-field>
    </div>
</template>
