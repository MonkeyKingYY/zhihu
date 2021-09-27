<template>
    <div class="container">
        <global-header :user="currentUser"></global-header>
        <column-list :list="testData"></column-list>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import "bootstrap/dist/css/bootstrap.min.css"
import ColumnList, { ColmunProps } from "./components/ColumnList.vue"
import GlobalHeader, { UserProps } from "./components/GlobalHeader.vue"
const currentUser: UserProps = {
    isLogin: true,
    name: "yee",
}
const testData: ColmunProps[] = [
    {
        id: 1,
        title: "test1的专栏",
        description: "这是test1的专栏，有一段非常有意思的简介，可以更新一下欧",
        avatar: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=275912806,2672201394&fm=26&gp=0.jpg",
    },
    {
        id: 2,
        title: "test2的专栏",
        description: "这是test2的专栏，有一段非常有意思的简介，可以更新一下欧",
        avatar: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=275912806,2672201394&fm=26&gp=0.jpg",
    },
    {
        id: 3,
        title: "test3的专栏",
        description: "这是test3的专栏，有一段非常有意思的简介，可以更新一下欧",
    },
    {
        id: 4,
        title: "test4的专栏",
        description: "这是test4的专栏，有一段非常有意思的简介，可以更新一下欧",
        avatar: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=275912806,2672201394&fm=26&gp=0.jpg",
    },
]
export default defineComponent({
    name: "App",
    components: {
        ColumnList,
        GlobalHeader,
    },
    setup() {
        return {
            testData,
            currentUser,
        }
    },
})
</script>

<style></style>
