<template>
    <div>
        <div class="header-container">
            <header-nav></header-nav>
            <header-content></header-content>
        </div>
    </div>
</template>

<script>
import HeaderNav from './HeaderNav.vue'
import HeaderContent from './HeaderContent.vue'

export default {
    name: 'app-header',
    components: {
        HeaderNav: HeaderNav,
        HeaderContent: HeaderContent
    }
}
</script>

<style scoped lang="scss">
    .header-container {
        background-image: url(/src/assets/images/header-bg.png);
    }
</style>