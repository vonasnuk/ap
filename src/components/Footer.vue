<template>
    <div>
        <footer>
            <div class="footer__container">
                <div class="footer__first__block">
                    <div class="first__block__title">
                        Блок 1
                    </div>
                    <div class="footer__mailing">
                        <p class="footer__mailing__title">Будьте в курсе новостей и новинок!</p>
                        <p class="footer__mailing__description">Подписывайтесь на рассылку</p>
                        <div class="footer__mailing__email">
                            <input placeholder="Укажите свой email для подписки" type="email" v-model="email">
                            <button v-on:click="validateEmail(email)">Подписаться</button>
                        </div>
                    </div>
                </div>
                <div class="link__block">
                    <div class="link__block__title">
                        Блок ссылок 1
                    </div>
                    <ul class="link__list">
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 1</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 2</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 3</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 4</a></li>
                    </ul>
                </div>
                <div class="link__block">
                    <div class="link__block__title">
                        Блок 2
                    </div>
                    <ul class="link__list">
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 1</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 2</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 3</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 4</a></li>
                    </ul>
                </div>
                <div class="link__block">
                    <div class="link__block__title">
                        Блок ссылок 2
                    </div>
                    <ul class="link__list">
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 1</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 2</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 3</a></li>
                        <li class="link__item"><a class="footer__link" href="#">Ссылка 4</a></li>
                    </ul>
                </div>
            </div>
            <div class="external__links">
                <img class="test__logo" src="../assets/test_1613.png">
                <p class="external__link__description">© Copyrith 2017. Тестовое задание Wezom</p>
                <div class="socials__link">
                    <a class="socials__link__item" href="#"><i class="fab fa-vk socials__link__icon"></i></a>
                    <a class="socials__link__item" href="#"><i class="fab fa-facebook-f socials__link__icon"></i></a>
                    <a class="socials__link__item" href="#"><i class="fab fa-twitter socials__link__icon"></i></a>
                    <a class="socials__link__item" href="#"><i class="fab fa-youtube socials__link__icon"></i></a>
                </div>
                <img class="wezom__logo" src="../assets/wezom-logo.png">
                <p class="external__link__description external__link__text">Разработка тестового <br> <span class="external__links__wezom">Wezom Agency</span></p>
            </div>
            <div class="popup" :class="{toggle: !togglePopup}">
                <div class="popup__content">
                    <p class="popup__text">Вы успешно подписаны на рассылку</p>
                    <div class="popup__btn" v-on:click="showPopup">
                        <p>Закрыть</p>
                    </div>
                </div>
                <i class="fal fa-times popup__close" v-on:click="showPopup"></i>
            </div>
        </footer>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                togglePopup: false,
                email: null
            }
        },
        methods:{
            showPopup(){
                this.togglePopup = !this.togglePopup
            },
            validateEmail(email){
                    let reg = /\S+@\S+\.\S+/;
                    if (reg.test(email)){
                        this.togglePopup = true
                }
            }
        }
    }
</script>


<style lang="scss" scoped>
    footer{
        position: relative;
        margin-top: 75px;
        width: 2135px;
        background-color: #696969;
        height: 341px;
    }
    .footer__container{
        display: flex;
        
        .footer__first__block{
            padding-left: 279px;
            .first__block__title{
                font-size: 20px;
                line-height: 36px;
                font-weight: 500;
                color: #cbcbcb;
                padding-top: 30px;
                border-bottom: 1px solid #797979;
            }
            .footer__mailing{
                .footer__mailing__title{
                    padding-top: 15px;
                    height: 16px;
                    font-size: 20px;
                    font-weight: 700;
                    text-transform: uppercase;
                    color: #cbcbcb;
                }
                .footer__mailing__description{
                    line-height: 0px;
                    font-size: 26px;
                    font-weight: 900;
                    text-transform: uppercase;
                    color: #ffffff;
                }
                .footer__mailing__email{
                    display: flex;
                    input{
                        padding-left: 30px;
                        width: 373px;
                        height: 48px;
                        background-color: #f5f5f5;
                        outline: none;
                        border: none;
                    }
                    button{
                        cursor: pointer;
                        width: 170px;
                        height: 50px;
                        background-color: #ff8900;
                        text-align: center;
                        font-size: 16px;
                        line-height: 40px;
                        font-weight: 700;
                        text-transform: uppercase;
                        color: #ffffff;
                        outline: none;
                        border: none;
                    }
                }
            }
        }
        .link__block{
            margin-left: 116px;
            margin-top: 34px;
            &:nth-child(3){
                margin-left: 92px;
            }
            &:nth-child(4){
                margin-left: 92px;
                padding-left: 76px;
            }
            .link__block__title{
                font-size: 20px;
                font-weight: 500;
                color: #cbcbcb;
                padding-bottom: 8px;
                border-bottom: 1px solid #797979;
            }
            .link__list{
                display: inline;
                
                .link__item{
                    list-style-type: none;
                    margin-bottom: 16px;
                    margin-top: 17px;
                    .footer__link{
                        font-size: 13px;
                        font-weight: 400;
                        text-decoration: underline;
                        color: #ffffff;
                    }
                }
            }
        }
    }
    .external__links{
        display: flex;
        margin-top: 42px;
        margin-left: 282px;
        .socials__link{
            margin-left: 216px;
            .socials__link__item{
                padding-right: 10px;
                .socials__link__icon{
                    width: 48px;
                    height: 48px;
                    border: 1px solid #7b8092;
                    color: white;
                    text-align: center;
                    line-height: 45px;
                    &:hover{
                        border: 1px solid #ffc925;
                    }
                }
            }
            
        }
        .test__logo{
            display: block;
            width: 195px;
            height: 37px;
            border-right: 1px solid #e4e4e4;
            padding-right: 23px;
        }
        .wezom__logo{
            width: 42px;
            height: 15px;
            margin-left: 220px;
            margin-top: 19px;
        }
        .external__links__wezom{
            font-size: 14px;
            font-weight: 400;
            color: #ffffff;
        }
        .external__link__text{
            border-left: 1px solid #e4e4e4;
            margin-left: 20px;
        }
        .external__link__description{
            font-size: 12px;
            font-weight: 400;
            color: #a0a9b2;
            padding-left: 16px;
        }
    }
    .popup{
        width: 100%;
        min-height: 100%;
        background-color: rgba(0,0,0,0.5);
        overflow: hidden;
        position: fixed;
        top: 0px;
        .popup__content{
            margin: 220px auto 0px auto;
            padding:10px;
            width: 378px;
            height: 160px;
            background-color: #ffffff;
            font-size: 21px;
            line-height: 40px;
            font-weight: 700;
            color: #3b3b3b;
            .popup__btn{
                cursor: pointer;
                width: 210px;
                height: 50px;
                background-color: #ff8900;
                margin-left: 81px;
                p{
                    font-size: 16px;
                    font-weight: 700;
                    text-align: center;
                    margin-top: 18px;
                    line-height: 48px;
                    color: #ffffff;
                }
            }
        }
        .popup__close{
            cursor: pointer;
            color: #ffffff;
            font-size: 27px;
            opacity: 0.8;
            position: fixed;
            right: 675px;
            top: 190px;
        }
    }
    .toggle{
        display: none;
    }

</style>