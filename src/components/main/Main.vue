<template>
    <div class="main-container">
        <h1 class="main-container__h1"><strong>Why</strong> do we use it?</h1>
        <p class="main-container__text">
            This sounded nonsense to Alice, so she said nothing, 
            but set off at once toward the Red Queen. To her surprise, 
            she lost sight of her in a moment.
        </p>
        <timer></timer>
    </div>
</template>

<script>
import Timer from './Timer';

export default {
    name: 'app-main',
    components: {
        Timer: Timer
    }
}
</script>

<style lang="scss">
    .main-container {
        padding: 210px 20px 113px;
        background: #F2F2F2;
        &__h1{
            font-weight: 300;
            font-size: 35px;
            line-height: 50px;
            text-align: center;
            letter-spacing: 1px;
            color: #282B31;
            padding-bottom: 17px;
            strong {
                font-weight: 800;;
            }
        }
        &__text {
            max-width: 570px;
            margin: 0 auto;
            font-weight: normal;
            font-size: 16px;
            line-height: 30px;
            text-align: center;
            color: #676C75;
        }
    }
</style>