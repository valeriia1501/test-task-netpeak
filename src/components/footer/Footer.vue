<template>
    <footer class="footer">
        <a href="#" class="footer__logo">AppStarter</a>
        <div class="footer__text">
            <div class="footer__text-createdby">
                Created with
                <svg style="width:12px;height:12px" viewBox="0 0 24 24">
                    <path fill="#FF4876" d="M12,21.35L10.55,20.03C5.4,15.36 2,12.27 2,8.5C2,5.41 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.08C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.41 22,8.5C22,12.27 18.6,15.36 13.45,20.03L12,21.35Z" />
                </svg> by
                <strong>Sergey Azovskiy</strong> 
            </div>
            <div class="footer__text-copyright">
                © AppStarter, 2017
            </div>
        </div>
        <div class="footer__links">
            <a href="#" class="footer__link footer__link--tw"><i class="fab fa-twitter"></i></a>
            <a href="#" class="footer__link footer__link--fb"><i class="fab fa-facebook-f"></i></a>
            <a href="#" class="footer__link footer__link--in"><i class="fab fa-instagram"></i></a>  
        </div>
    </footer>
</template>

<style lang="scss" scoped>
    .footer {
        display: flex;
        justify-content: space-between;
        max-width: 1400px;
        margin: 0 auto;
        padding: 25px 0 30px;
        &__logo {
            font-weight: 800;
            font-size: 20px;
            line-height: 35px;
            color: #282B31;
            text-decoration: none;
        }
        &__text {
            padding-top: 10px;
            &-createdby {
                font-weight: normal;
                font-size: 11px;
                line-height: 22px;
                color: #999EA8;
                strong {
                    color: #282B31;
                    font-weight: bold;
                }
            }
            &-copyright {
                font-weight: normal;
                font-size: 11px;
                line-height: 22px;
                text-align: center;
                color: #999EA8;
            }
        }
        &__links {
            display: flex;
        }
        &__link {
            width: 40px;
            height: 40px;
            background: #FFFFFF;
            border: 1px solid #E7E8EA;
            box-sizing: border-box;
            color: #B9BDC3;
            display: flex;
            text-decoration: none;
            i {
                margin: auto;
            }
        }
        &__link--tw {
            border-radius: 6px 0px 0px 6px;
        }
        &__link--in {
            border-radius: 0px 6px 6px 0px;
        }
    }
</style>