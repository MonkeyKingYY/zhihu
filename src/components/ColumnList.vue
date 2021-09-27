<!--  -->
<template>
    <div class="row">
        <div v-for="column in columnList" :key="column.id" class="col-4">
            <div class="card h-100 shadow-sm">
                <div class="card-body text-center">
                    <img :src="column.avatar" :alt="column.title" class="card-img-top" />
                    <h5 class="card-title">{{ column.title }}</h5>
                    <p class="card-text text-left">{{ column.description }}</p>
                    <a href="#" class="btn btn-outline-primary">进入专栏</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType, computed } from "vue"
export interface ColmunProps {
    id: number
    title: string
    avatar?: string
    description: string
}
export default defineComponent({
    name: "ColumnList",
    props: {
        list: {
            type: Array as PropType<ColmunProps[]>,
            required: true,
        },
    },
    setup(props) {
        const columnList = computed(() => {
            return props.list.map(column => {
                if (!column.avatar) {
                    column.avatar = require("@/assets/column.jpg")
                }
                return column
            })
        })
        return {
            columnList,
        }
    },
})
</script>
<style scoped>
.card-body img {
    width: 380px;
    height: 250px;
}
</style>
