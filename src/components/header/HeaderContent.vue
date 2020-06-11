<template>
    <div class="header-content">
        <div class="header-content__info">
            <img src="/src/assets/images/app-icon.png" class="header-content__info-icon">
            <div class="header-content__info-text">
                <strong>AppStarter.</strong> Best landing page for web and mobile apps 
            </div>
            <div class="header-content__info-buttons">
                <button class="header-content__info-download">Download Now</button>
                <button class="header-content__info-video">Watch Video</button>
            </div>
        </div>
        <div class="header-content__tablet">
            <div class="header-content__tablet-base">
                <div class="header-content__tablet-content"></div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    $primaryColor: #FFFFFF;
    $secondaryColor: #282B31;

    .header-content {
        display: flex;
        max-width: 1400px;
        margin: 0 auto;
        &__info {
            width: 50%;
            padding-top: 150px;
            &-text {
                padding-top: 10px;
                max-width: 555px;
                color: $primaryColor;
                font-weight: 300;
                font-size: 35px;
                line-height: 50px;
                letter-spacing: 1px;
                strong {
                  font-weight: 800;  
                }
            }
            &-buttons {
                padding: 30px 0 190px;
            }
            &-download {
                color: $primaryColor;
                padding: 15px;
                background: linear-gradient(163.33deg, #FF8E64 0%, #FFE641 100%);
                border-radius: 6px;
                border-style: none;
                cursor: pointer;
                margin-right: 10px;
            }
            &-video {
                color: $secondaryColor;
                padding: 15px;
                background: $primaryColor;
                border-radius: 6px;
                border-style: none;
                cursor: pointer;
                margin-left: 10px;
            }
        }
        &__tablet {
            width: 50%;
            &-base {
                width: 470px;  
                background: linear-gradient(180deg, rgba(255, 255, 255, 0.0001) 96.24%, rgba(32, 33, 39, 0.03) 100%), #FFFFFF;
                box-shadow: inset 0px -2px 6px rgba(40, 43, 49, 0.06);
                border-radius: 30px;
                margin-bottom: -100px;
                margin-top: 60px;
                margin: 60px 0 -120px 70px; 
                padding: 62px 0;  
            }
            &-content {
                width: 434px;
                height: 581px;
                background: url("/src/assets/images/tablet-inner.png");
                margin: 0 17px;
            }
        }
    }
</style>