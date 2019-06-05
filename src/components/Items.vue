<template>
    <div>
        <span @click="toggle">
            {{ model.menuName }}
        </span>
        <ul v-if="isFolder" v-show="isShow">
            <items v-for="(item, index) in model.childTree" :model="item" :key="index"></items>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'items',
        props: ['model'],
        data() {
            return {
                isShow: false
            }
        },
        computed: {
            isFolder() {
                return this.model.childTree && this.model.childTree.length;
            }
        },
        methods: {
            toggle() {
                this.isShow = !this.isShow;
            }
        },
    }
</script>

<style scoped>

</style>