<template>
    <section class="header">
        <h1 class="title">Awesome Github Profile</h1>
        <nav class="navbar">
            <NavItem
                v-for="category in categories"
                :key="category.categoryName"
                :title="category.categoryName"
                :active="selectedCategory === category.categoryName"
                @click="setSelectedCategory(category.categoryName)"
            />
        </nav>
    </section>
</template>

<script>
import NavItem from './NavItem.vue'
import { defineComponent } from 'vue'
import { useStoreInject } from '../hooks/store'

export default defineComponent({
    components: { NavItem },
    setup() {
        const {
            categories,
            loading,
            selectedCategory,
            setSelectedCategory,
        } = useStoreInject()

        return {
            categories,
            loading,
            selectedCategory,
            setSelectedCategory,
        }
    },
})
</script>

<style lang="less" scoped>
.header {
    background-color: #fdfdfd;
    border-bottom: 1px solid #ebebeb;
}
.header .title {
    text-align: center;
    font-size: 28px;
    margin: 0;
    padding: 50px 0;
    padding-bottom: 30px;
    color: #333;
}
.navbar {
    width: 900px;
    margin: 0 auto;
    margin-bottom: 30px;
}</style
>2
