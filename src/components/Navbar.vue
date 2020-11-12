<template>
    <div>
        <nav class="nav">
            <ul class="nav__list">
                <li class="nav__item"><a class="nav__link" href="#">Главная</a></li>
                <li class="nav__item"><a class="nav__link" href="#">О компании</a></li>
                <li class="nav__item"><a class="nav__link" href="#">Ссылка 1</a></li>
                <li class="nav__item"><a class="nav__link" href="#">Ссылка 2</a></li>
                <li class="nav__item"><a class="nav__link" href="#">Ссылка 3</a></li>
                <div class="nav__btn" v-on:click="showLoginPopup">
                    <img class="nav__img" src="../assets/vector20.png" alt='image logo user'>
                    <p class="nav__text">Вход</p>
                </div>
            </ul>
        </nav>
        <div class="popup__login" :class="{toggle: toggleLoginPopup}">
            <div class="popup__content">
                <div class="popup__left__block">
                    <div class="popup__title">
                        Вход в личный кабинет
                    </div>
                    <form action="">
                        <p class="login__text">Ваш email</p>
                        <input v-on:keyup="validateEmail(email)" v-model="email" placeholder="mikel_ivanov98@gmail.com" class="input__text" type="email">
                        <p class="login__text">Пароль</p>
                        <input v-on:keyup="validateEmail(email)" v-model="password" placeholder="*************" class="input__text" type="password" autocomplete="on">
                        <br>
                        <input class="input__checkbox" type="checkbox" id="remember" name="remember">
                        <label for="remember">Запомнить меня</label>
                        <div class="recovery">
                            <a href="#">Забыли пароль?</a>
                            <a href="#">Регистрация</a>
                        </div>
                    </form>
                    <button class="popup__btn" :class="{popup__btn__active: activeLoginButtun}">
                        <p>Войти в личный кабинет</p>
                    </button>
                </div>
                <div class="popup__right__block">
                    <div class="popup__title">
                        Войти с помощью
                    </div>
                    <div class="login__btn facebook__login">
                        <i class="fab fa-facebook-f"> Facebook</i>
                        
                    </div>
                    <div class="login__btn twitter__login">
                        <i class="fab fa-twitter"> Twitter</i>
                    </div>
                    <div class="login__btn google__login">
                        <i class="fab fa-google"> Google</i>
                    </div>
                </div>
            </div>
            <i v-on:click="showLoginPopup" class="fal fa-times popup__close"></i>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                toggleLoginPopup: true,
                email: null,
                password: '',
                activeLoginButtun: false
            }
        },
        methods:{
            showLoginPopup(){
                this.toggleLoginPopup = !this.toggleLoginPopup
                this.activeLoginButtun = false
            },
            validateEmail(email){
                    let reg = /\S+@\S+\.\S+/;
                    if ((reg.test(email)) && (this.password.length >= 4)){
                        this.activeLoginButtun = true
                    }
                    else this.activeLoginButtun = false
            }
        }
    }
</script>

<style lang="scss" scoped>
    .nav{
        width: 1920px;
        margin: 0;
        padding: 0;
        padding-left: 215px;
        overflow: hidden;
        background-color: #696969;
        height: 50px;
        .nav__list{
            margin: 0;
            list-style-type: none;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            .nav__btn{
                cursor: pointer;
                display: flex;
                height: 50px;
                width: 124px;
                margin-left: auto;
                margin-right: 495px;
                background-color: #ff8900;
                .nav__img{
                    align-self: center;
                    margin-left: 34px;
                    margin-bottom: 5px;
                }
                .nav__text{
                    margin-left: 10px;
                    font-size: 12px;
                    line-height: 20px;
                    font-weight: 400;
                    text-transform: uppercase;
                    color: #ffffff;
                    align-self: center;
                }
            }
            .nav__item{
                height: 32px;
                width: 106px;
                text-align: center;
                margin-top: 16px;
                &:hover{
                    border-bottom: 2px solid #ffc925;
                }
                .nav__link{
                    text-decoration: none;
                    font-size: 12px;
                    line-height: 20px;
                    font-weight: 400;
                    text-transform: uppercase;
                    color: #c2c2c2;
                    &:hover{
                        color: #ffffff;
                    }
                }
            }
        }
    }
    .popup__login{
        width: 100%;
        min-height: 100%;
        background-color: rgba(0,0,0,0.5);
        overflow: hidden;
        position: fixed;
        top: 0px;
        z-index: 100;
        .popup__content{
            display: flex;
            margin: 220px auto 0px auto;
            background-color: #ffffff;
            font-size: 21px;
            line-height: 40px;
            font-weight: 700;
            color: #3b3b3b;
            width: 755px;
            height: 431px;
            .popup__title{
                font-size: 24px;
                font-weight: 700;
                color: #3b3b3b;
            }
            .popup__left__block{
                margin: 34px 0 34px 43px; 
                width: 385px;
                border-right: 1px solid #e9e9e9;
                .input__text{
                    padding-left: 14px;
                    width: 299px;
                    height: 40px;
                    background-color: #ffffff;
                    border: 1px solid #d2d2d2;
                }
                .input__checkbox{
                    width: 16px;
                    height: 16px;
                    background-color: #ffffff;
                    border: 1px solid #d2d2d2;
                }
                label{
                    font-size: 14px;
                    font-weight: 400;
                    color: #3d3d3d;
                }
                .login__text{
                    margin: 0;
                    font-size: 14px;
                    font-weight: 400;
                    color: #3b3b3b;
                }
                .recovery{
                    display: flex;
                    font-size: 14px;
                    font-weight: 400;
                    text-decoration: underline;
                    a{
                        margin-right: 20px;
                        color: #3d3d3d;
                    }
                }
                .popup__btn{
                    margin-top: 20px;
                    width: 210px;
                    height: 50px;
                    background-color: #afb9c6;
                    border: none;
                    &:focus, &:active{
                        outline: none;
                    }
                    p{
                        font-size: 14px;
                        font-weight: 400;
                        color: #ffffff;
                    }
                }
                .popup__btn__active{
                    cursor: pointer;
                    background-color: #ff8900;
                }
            }
            .popup__right__block{
                margin-top: 34px;
                margin-left: 16px;
                .login__btn{
                    cursor: pointer;
                    width: 293px;
                    height: 50px;
                    font-size: 14px;
                    line-height: 40px;
                    font-weight: 400;
                    color: #ffffff;
                    line-height: 50px;
                    margin-bottom: 23px;
                    i{
                        padding-left: 107px;
                    }
                }
                .facebook__login{
                    background-color: #3b5998;
                    margin-top: 48px;
                }
                .twitter__login{
                    background-color: #41abe1;
                }
                .google__login{
                    background-color: #ea4335;
                }
            }
        }
        .popup__close{
            cursor: pointer;
            color: #ffffff;
            font-size: 27px;
            opacity: 0.8;
            position: fixed;
            right: 498px;
            top: 190px;
        }
    }
    .toggle{
        display: none;
    }
    
</style>