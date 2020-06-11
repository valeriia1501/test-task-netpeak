<template>
    <div class="header-nav">
        <a href="#" class="header-nav__logo">AppStarter</a>
        <div class="header-nav__container">
            <div class="header-nav__container-items">
                <a href="#" v-for="item in navItems" :key="item">
                    {{item}}
                </a>
            </div>
            <button class="header-nav__container-button">GET IT FREE</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'header-nav',
        data () {
            return {
              navItems: ['Features', 'Video Tour', 'Reviews', 'Pricing']
            }
        },
    }
</script>

<style scoped lang="scss">
    $primaryColor: #FFFFFF;
    $secondaryColor: #282B31;

    .header-nav {
        display: flex;
        max-width: 1400px;
        margin: 0 auto;
        padding: 30px 0;
        &__logo {
            width: 50%;
            color: $primaryColor;
            font-weight: 800;
            font-size: 20px;
            line-height: 27px;
            text-decoration: none;

        }
        &__container {
            width: 50%;
            display: flex;
            justify-content: center;
            &-items {
                a {
                    color: $primaryColor;
                    font-weight: normal;
                    font-size: 15px;
                    line-height: 32px;
                    padding-right: 31px;
                    text-decoration: none;
                }
            }
            &-button {
                background-color: $primaryColor;    
                border-radius: 6px;
                border-color: $primaryColor;
                padding: 8px 14px;
                color: $secondaryColor;
                border-style: none;
                cursor: pointer;
            }
        }
    }
</style>