<template>
    <div class="menu">
        <div class="menu__header">
            <div class="menu__btn">
                <img class="burger__img" src="../assets/burger.png" alt="burger">
            </div>
            <div class="header__text">
                <p>Меню</p>
            </div>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 1</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 2</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 3</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 4</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 5</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 6</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
        <div class="menu__item">
            <a href="#">Ссылка 7</a>
            <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
    </div>
</template>

<style lang='scss' scoped>
    .menu{
        height: 450px;
        width: 326px;
        margin-left: 278px;
        margin-top: 19px;
        .menu__header{
            display: flex;
            height: 56px;
            .menu__btn{
                cursor: pointer;
                width: 62px;
                height: 56px;
                background-color: #db7200;
                &:hover{
                    background-color: #ffa100;
                }
                .burger__img{
                        padding-top: 22px;
                        padding-left: 25px;
                }
            }
            .header__text{
                width: 264px;
                height: 56px;
                background-color: #ffa100;
                p{
                    font-size: 20px;
                    line-height: 20px;
                    font-weight: 700;
                    color: #ffffff;
                    margin-left: 22px;
                }
            }
        }
        .menu__item{
            display: flex;
            height: 53px;
            cursor: pointer;
            border-bottom: 1px solid #e4e4e4;
            a{
                text-decoration: none;
                padding-top: 18px;
                padding-left: 41px;
                font-size: 16px;
                font-weight: 700;
                text-transform: uppercase;
                color: #3b3b3b;
            }
            i{
                margin-left: 162px;
                margin-top: 23px;
                color: #c0c4d8;
            }
        }
}
</style>