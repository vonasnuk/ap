<template>
    <div>
        <div class="container">
            <div class="logo">
                <a href="#"><img src="../assets/logo.png" alt=""></a>
            </div>
            <div class="phone">
                <div class="phone__number">
                    +380 98 170 00 740
                </div>
                <div class="phone__number">
                    +380 98 170 00 740
                </div>
                <div class="phone__callback" v-on:click="showCallbackPopup">
                    <img src="../assets/phone-logo.png" alt="">
                    <div class="phone__text">
                        Перезвонить мне
                    </div>
                </div>
            </div>
            <div class="header-actions">
                <div class="header-actions__item">
                    <div v-if="counter.counterComparison > 0" class="counter__added">
                        <img src="../assets/counter-icon.png" alt="counter img">
                        <span>{{counter.counterComparison}}</span>
                    </div>
                    <div class="actions__btn">
                        <img src="../assets/header-icon1.png" alt="header img">
                        <p>сравнение</p>
                    </div>
                </div>
                <div class="header-actions__item">
                    <div v-if="counter.counterFavorites > 0" class="counter__added">
                        <img src="../assets/counter-icon.png" alt="counter img">
                        <span>{{counter.counterFavorites}}</span>
                    </div>
                    <div class="acton__btn">
                        <img src="../assets/header-icon2.png" alt="header img">
                        <p>избранное</p>
                    </div>
                </div>
                <div class="header-actions__item">
                    <div v-if="counter.counterBasket > 0" class="counter__added">
                        <img src="../assets/counter-icon.png" alt="counter img">
                        <span>{{counter.counterBasket}}</span>
                    </div>
                    <div class="acton__btn">
                        <img src="../assets/header-icon3.png" alt="header img">
                        <p>корзина</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="popup__callback" :class="{toggle: showPopupCallback}">
            <div class="popup__callback__content">
                <div class="popup__callback__container">
                    <div class="callback__content__title">Перезвоните мне</div>
                    <p class="callback__content__text">Номер телефона</p>
                    <input class="callback__content__phone" type="text" :value="value" v-imask="mask" @accept="onAccept" >
                    <button class="callback__content__btn" :class="{callback__content__btn__active: calbackButtonActive}" v-on:click="validatePhone(value)">
                        <p>Перезвоните мне</p>
                    </button>
                </div>
            </div>
            <i class="fal fa-times popup__close" v-on:click="showCallbackPopup"></i>
        </div>
    </div>
</template>


<script>
    import {IMaskDirective} from 'vue-imask'

    export default{
        props: ['counter'],
        data(){
            return{
                value: '',
                mask: {
                    mask: '+38(000)000-00-00',
                    lazy: false
                },
                calbackButtonActive: false,
                showPopupCallback: true
            }
        },
        methods:{
            onAccept (e) {
                const maskRef = e.detail;
                this.value = maskRef.value;
            },  
            validatePhone(value){
                if (value.length > 16){
                    this.calbackButtonActive = !this.calbackButtonActive
                    this.showPopupCallback = !this.showPopupCallback
                    this.value = ''
                }
            },
            showCallbackPopup(){
                this.showPopupCallback = !this.showPopupCallback
            }
        },
        directives: {
            imask: IMaskDirective
        }
    }
</script>

<style lang="scss" scoped>
    .container{
        width: 1365px;
        height: 64px;
        display: flex;
        margin-left: 280px;
        margin-top: 42px;
        .phone{
            display: flex;
            align-items: center;
            margin-left: 150px;
            background-color: #f5f5f5;
            width: 575px;
            height: 49px;
            .phone__number{
                font-style: italic;
                font-weight: bold;
                margin-bottom: 5px;
                margin-left: 9px;
                margin-right: 30px;
            }
            .phone__callback{
                cursor: pointer;
                display: flex;
                width: 197px;
                height: 49px;   
                background-color: #ff8900;
                margin-left: 12px;
                img{
                    margin-left: 30px;
                    align-self: center;
                    margin-bottom: 3px;
                }
                .phone__text{
                    color: #ffffff;
                    letter-spacing: -0.9px;
                    margin-left: 10px;
                    align-self: center;
                    font-size: 12px;
                    font-weight: 400;
                    text-transform: uppercase;
                    color: #ffffff;
                }
            }
        }
        .header-actions{
            height: 58px;
            width: 51px;
            display: flex;
            margin-left: 94px;  
            .header-actions__item{
                cursor: pointer;
                margin-left: 30px;
                padding-right: 27px;
                text-align: center;
                border-right: 1px solid #e4e4e4;
                height: 64px;
                p{
                    font-size: 10px;
                    line-height: 2px;
                    font-weight: 400;
                    text-transform: uppercase;
                    color: #3d3d3d;
                }
                .actions__btn{
                    z-index: 1;
                }
            }
            .counter__added{
                position: absolute;
                z-index: 50;
                img{
                    z-index: 60;
                    position: absolute;
                    bottom: -5px;
                    left: 11px;
                }
                span{
                    color: white;
                    left: 25px;
                    bottom: 5px;
                    z-index: 65;
                    position: absolute;
                    font-size: 11px;
                    line-height: 20px;
                    font-weight: 400;
                    text-transform: uppercase;
                }
            }
        }
    }
    .popup__callback{
        width: 100%;
        min-height: 100%;
        background-color: rgba(0,0,0,0.5);
        overflow: hidden;
        position: fixed;
        top: 0px;
        z-index: 100;
        .popup__close{
            cursor: pointer;
            color: #ffffff;
            font-size: 27px;
            opacity: 0.8;
            position: fixed;
            right: 675px;
            top: 190px;
        }
        .popup__callback__container{
            padding-top: 35px;
            padding-left: 38px;
        }
        .popup__callback__content{
            margin: 220px auto 0px auto;
            width: 378px;
            height: 283px;
            background-color: #ffffff;
            .callback__content__title{
                font-size: 24px;
                font-weight: 700;
                color: #3b3b3b;
            }
            .callback__content__text{
                padding-top: 19px;
                padding-bottom: 11px;
                font-size: 14px;
                font-weight: 400;
                color: #3b3b3b;
            }
            .callback__content__phone{
                padding-left: 14px;
                font-size: 16px;
                font-weight: 400;
                color: #9c9c9c;
                width: 299px;
                height: 40px;
                background-color: #ffffff;
                border: 1px solid #d2d2d2;
            }
            .callback__content__btn{
                margin-top: 21px;
                margin-left: 51px;
                width: 210px;
                height: 50px;
                background-color: #ff8900;
                border: none;
                p{
                    font-size: 14px;
                    font-weight: 400;
                    color: #ffffff;
                }
            }
            .callback__content__btn__active{
                cursor: pointer;
            }
        }
    }
    .toggle{
        display: none;
    }
</style>