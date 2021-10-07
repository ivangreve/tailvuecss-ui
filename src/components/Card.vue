<template>
    <div v-if="this.cardVisible" class="w-full grid grid-cols-1 md:grid-cols-2 gap-6 m-2 ">
        <div class="relative bg-white shadow-lg rounded-lg p-6">
            <div class="absolute top-0 right-0">
                <button class="rounded-full m-1 h-7 w-7 flex items-center justify-center font-semibold text-gray-500 hover:bg-gray-200">
                    X
                </button>

            </div>
            <div class="flex items-center space-x-6 mb-4">
                <img v-if="this.image !== ''" class="h-28 w-28 object-cover object-center rounded-full" 
                :src="this.image" alt="photo">
                <div>
                    <slot name="title">
                        <p class="text-xl text-gray-700 font-normal mb-1">{{this.title}}</p>
                    </slot>
                    <slot name="subtitle">
                        <p class="text-base text-blue-600 font-semibold">{{this.subtitle}}</p>
                    </slot>
                </div>
            </div>
            <div>
                <slot>
                    <p :v-if="this.content != ''" class="text-gray-400 leading-loose font-normal text-base">
                        {{this.content}}
                    </p>
                </slot>

            </div>
        </div>
    </div>

</template>

<script>
import { ref, computed, h } from 'vue'

export default {
    props: {
        title: {
            type: String,
            required: false,
            default: "Card Title"
        },
        subtitle: {
            type: String,
            required: false,
            default: "Card Subtitle"
        },
        content: {
            type: String,
            required: false,
            default: ""
        },
        image: {
            type: String,
            required: false,
            defalt: ""
        },
        tailwindClass: {
            type: String,
            required: false,
            default: ""
        },
        closed: {
            type: Boolean,
            required: false,
            default: false
        }
    },
    setup() {
        const cardVisible = ref(true);
        return { cardVisible }
    },

}
</script>
