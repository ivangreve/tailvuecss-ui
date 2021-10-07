<template>
    <button :class="this.typeClasses[this.type] + this.tailwindClass" v-on:click="this.onClick">
        {{this.text}}
    </button>

</template>

<script>
import { ref, computed } from 'vue'

export default {
    props: {
        text: {
            type: String,
            required: false,
            default: "Button"
        },
        type: {
            type: String,
            required: false,
            default: "default"
        },
        onClick: {
            type: Function,
            required: false,
            default: () => {}
        },
        tailwindClass: {
            type: String,
            required: false,
            default: ""
        }
    },
    setup() {
        let dicTypeClasses = {
            default: "bg-blue-500 hover:bg-blue-600 text-white rounded-lg px-8 py-2 m-2 shadow-md font-semibold ",
            success: "bg-green-600 hover:bg-green-700 text-white rounded-lg px-8 py-2 m-2 shadow-md font-semibold ",
            warning: "bg-yellow-500 hover:bg-yellow-600 text-white rounded-lg px-8 py-2 m-2 shadow-md font-semibold ",
            error: "bg-red-600 hover:bg-red-700 text-white rounded-lg px-8 py-2 m-2 shadow-md font-semibold "
        }
        let typeClasses = ref(dicTypeClasses);

        return { typeClasses }
    },

}
</script>
