<template>
    <main>
        <div class="container">
            <div class="cards__title">
                Карточки товаров
                <div class="card__link">
                    <a href="#">Ссылка в каталог</a>
                    <div class="orange__line"></div>
                </div>
            </div>
       
            <div class="product__container">
                <div class="product__card">
                    <div class="product__tags">
                        Mark
                    </div>
                    <div class="product__name">
                        Антифриз Fosser Antifreeze <br> FA 12 Readymix 1 л Concentart, Germany
                    </div>
                    <div class="card__row">
                        <div class="product__rating">
                            <span class="active"></span>	
                            <span class="active"></span>    
                            <span class="active"></span>  
                            <span class="active"></span>    
                            <span class="active"></span>  
                        </div>
                        <div class="product__reviews">
                            <a href="#">Отзывы (10)</a>
                        </div>
                        <div class="product__availability">
                            В наличии: 24 шт.
                        </div>
                    </div>
                    <div class="product__info">
                        <div class="product__info__icon">
                            <img src="../assets/product-sun-icon.png" alt="">
                            <p>Летняя</p>
                            <img src="../assets/product-car-icon.png" alt="">
                            <p>Легковая</p>
                            <img src="../assets/product-new-icon.png" alt="">
                            <p>Новая</p>
                        </div>
                        <div class="product__info__img">
                            <img src="../assets/products/1.png" alt="">
                        </div>
                    </div>
                    <div class="product__labels">
                        <img src="../assets/label-new.png" alt="">
                        <img src="../assets/label-hit.png" alt="">
                        <img src="../assets/label-discount.png" alt="">
                    </div>
                    <div class="product__price">
                        <p class="product__price__new">599 <span>грн.</span></p>
                        <p class="product__price__old">1 250 грн.</p>
                    </div>
                    <div class="product__buy__btn" v-on:click='updateBasket'>
                        <img src="../assets/basket-icon.png" alt="">
                        <div class="product__buy__text">Купить товар</div>
                    </div>
                    <div class="product__comparison__row" v-on:click="updateCount">
                        <div class="product__comparison">
                            <img src="../assets/icon4.png" alt="">
                            <p v-on:click="updateText($event)">Сравнить товар</p>
                        </div>
                        <div class="product__favourites" v-on:click="updateCount">
                            <img src="../assets/icon5.png" alt="">
                            <p v-on:click="updateText($event)">В избранное</p>
                        </div>
                    </div>
                </div>

                <div class="product__card">
                    <div class="product__tags">
                        Mark
                    </div>
                    <div class="product__name">
                        Антифриз Fosser Antifreeze <br> FA 12 Readymix 1 л Concentart, Germany
                    </div>
                    <div class="card__row">
                        <div class="product__rating">
                            <span class="active"></span>	
                            <span class="active"></span>    
                            <span class="active"></span>  
                            <span></span>
                            <span></span>
                        </div>
                        <div class="product__reviews">
                            <a href="#">Отзывы (10)</a>
                        </div>
                        <div class="product__availability">
                            В наличии: 24 шт.
                        </div>
                    </div>
                    <div class="product__info">
                        <div class="product__info__icon">
                            <img src="../assets/product-sun-icon.png" alt="">
                            <p>Летняя</p>
                            <img src="../assets/product-new-icon.png" alt="">
                            <p>Новая</p>
                        </div>
                        <div class="product__info__img">
                            <img src="../assets/products/2.png" alt="">
                        </div>
                    </div>
                    <div class="product__labels">
                        <img src="../assets/label-new.png" alt="">
                        <img src="../assets/label-hit.png" alt="">
                    </div>
                    <div class="product__price">
                        <p class="product__price__new">599 <span>грн.</span></p>
                        <p class="product__price__old">1 250 грн.</p>
                    </div>
                    <div class="product__buy__btn" v-on:click='updateBasket'>
                        <img src="../assets/basket-icon.png" alt="">
                        <div class="product__buy__text">Купить товар</div>
                    </div>
                    <div class="product__comparison__row" v-on:click="updateCount">
                        <div class="product__comparison">
                            <img src="../assets/icon4.png" alt="">
                            <p ref="productComparisonText" v-on:click="updateText($event)">Сравнить товар</p>
                        </div>
                        <div class="product__favourites" v-on:click="updateCount">
                            <img src="../assets/icon5.png" alt="">
                            <p v-on:click="updateText($event)">В избранное</p>
                        </div>
                    </div>
                </div>

                <div class="product__card">
                    <div class="product__tags">
                        Mark
                    </div>
                    <div class="product__name">
                        Антифриз Fosser Antifreeze <br> FA 12 Readymix 1 л Concentart, Germany
                    </div>
                    <div class="card__row">
                        <div class="product__rating">
                            <span></span>
                            <span></span>
                            <span></span>
                            <span></span>
                            <span></span> 
                        </div>
                        <div class="product__reviews">
                            <a href="#">Без отзывов</a>
                        </div>
                        <div class="product__availability">
                            В наличии: 24 шт.
                        </div>
                    </div>
                    <div class="product__info">
                        <div class="product__info__icon">
                            <img src="../assets/product-sun-icon.png" alt="">
                            <p>Летняя</p>
                            <img src="../assets/product-car-icon.png" alt="">
                            <p>Легковая</p>
                            <img src="../assets/product-new-icon.png" alt="">
                            <p>Новая</p>
                        </div>
                        <div class="product__info__img">
                            <img src="../assets/products/3.png" alt="">
                        </div>
                    </div>
                    <div class="product__labels">
                        <img src="../assets/label-new.png" alt="">
                    </div>
                    <div class="product__price">
                        <p class="product__price__new">599 <span>грн.</span></p>
                        <p class="product__price__old">1 250 грн.</p>
                    </div>
                    <div class="product__buy__btn" v-on:click='updateBasket'>
                        <img src="../assets/basket-icon.png" alt="">
                        <div class="product__buy__text">Купить товар</div>
                    </div>
                    <div class="product__comparison__row" v-on:click="updateCount">
                        <div class="product__comparison">
                            <img src="../assets/icon4.png" alt="">
                            <p v-on:click="updateText($event)">Сравнить товар</p>
                        </div>
                        <div class="product__favourites" v-on:click="updateCount">
                            <img src="../assets/icon5.png" alt="">
                            <p v-on:click="updateText($event)">В избранное</p>
                        </div>
                    </div>
                </div>

                <div class="product__card right__border--none">
                    <div class="product__tags">
                        Mark
                    </div>
                    <div class="product__name">
                        Антифриз Fosser Antifreeze <br> FA 12 Readymix 1 л Concentart, Germany
                    </div>
                    <div class="card__row">
                        <div class="product__rating">
                            <span class="active"></span>	
                            <span class="active"></span>    
                            <span class="active"></span>  
                            <span class="active"></span>    
                            <span class="active"></span>  
                        </div>
                        <div class="product__reviews">
                            <a href="#">Отзывы (10)</a>
                        </div>
                        <div class="product__availability">
                            В наличии: 24 шт.
                        </div>
                    </div>
                    <div class="product__info">
                        <div class="product__info__icon">
                            <img src="../assets/product-sun-icon.png" alt="">
                            <p>Летняя</p>
                            <img src="../assets/product-car-icon.png" alt="">
                            <p>Легковая</p>
                        </div>
                        <div class="product__info__img">
                            <img src="../assets/products/4.png" alt="">
                        </div>
                    </div>
                    <div class="product__labels">
                    </div>
                    <div class="product__price">
                        <p class="product__price__new">599 <span>грн.</span></p>
                        <p class="product__price__old">1 250 грн.</p>
                    </div>
                    <div class="product__buy__btn" v-on:click='updateBasket'>
                        <img src="../assets/basket-icon.png" alt="">
                        <div class="product__buy__text">Купить товар</div>
                    </div>
                    <div class="product__comparison__row" v-on:click="updateCount">
                        <div class="product__comparison">
                            <img src="../assets/icon4.png" alt="">
                            <p v-on:click="updateText($event)">Сравнить товар</p>
                        </div>
                        <div class="product__favourites" v-on:click="updateCount">
                            <img src="../assets/icon5.png" alt="">
                            <p v-on:click="updateText($event)">В избранное</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    export default{
        data(){
            return{
                counterComparison: 0,
                counterFavorites: 0,
                counterBasket: 0
            }
        },
        methods:{
            updateText(e){
                if (e.target.innerHTML === 'Сравнить товар'){
                    e.target.innerHTML = 'В сравнении'
                    this.counterComparison++
                }
                else if (e.target.innerHTML === 'В избранное'){
                    e.target.innerHTML = 'В избранном'
                    this.counterFavorites++
                }
            },
            updateBasket(){
                this.counterBasket++
                this.updateCount()
            },
            updateCount(){
                this.$emit('updateCount', {
                    counterComparison: this.counterComparison,
                    counterFavorites: this.counterFavorites,
                    counterBasket: this.counterBasket
                })
            }
        }
    }
</script>


<style lang="scss" scoped>
.container{
    width: 1760px;
    .card__link{
        display: flex;
        font-size: 14px;
        line-height: 50px;
        font-weight: 400;
        text-decoration: underline;
        padding-left: 909px;
        a{
            color: #000000;
        }
        .orange__line{
            margin-top: 25px;
            margin-left: 11px;
            width: 12px;
            height: 1px;
            background-color: #ff8500;
        }
    }
}
.product__container{
    display: flex;
    margin-left: 275px;
}
    .cards__title{
        display: flex;
        margin-left: 275px;
        font-size: 36px;
        font-weight: 400;
        color: #3b3b3b;
        margin-top: 29px;
    }
    .product__card{
        padding-right: 12px; 
        padding-left: 11px;
        height: 570px;
        border: 2px solid #e4e4e4;
        border-left: none;
        .product__tags{
            padding-top: 3px;
            text-align: center;
            width: 79px;
            height: 22px;
            background-color: #f2f2f2;
            font-size: 14px;
            font-weight: 300;
            color: #848484;
            margin-top: 33px;
        }
        .product__name{
            cursor: pointer;
            padding-top: 11px;
            font-size: 17px;
            font-weight: 400;
            line-height: 26px;
            text-decoration: underline;
            color: #3b3b3b;
        }
        .card__row{
            margin-top: 10px;
            display: flex;
            .product__reviews a{
                font-size: 13px;
                font-weight: 400;
                text-decoration: underline;
                color: #9b9b9b;
                margin-left: 9px;
            }
            .product__availability{
                font-size: 12px;
                font-weight: 400;
                color: #757575;
                margin-left: 33px;
            }
        }
        .product__labels{
            display: flex;
            justify-content: center;
            min-height: 46px;
            margin-bottom: -12px;
            margin-left: 17px;
        }
        .product__price{
            display: flex;
            .product__price__new{
                line-height: 0px;
                font-size: 30px;
                font-weight: 900;
                font-style: italic;
                text-transform: uppercase;
                color: #3b3b3b;
                span{
                    font-size: 18px;
                    letter-spacing: 0.05em;
                }
            }
            .product__price__old{
                font-size: 16px;
                font-weight: 900;
                font-style: italic;
                text-transform: uppercase;
                color: #989898;
                text-decoration: line-through;
                text-decoration-color: red;
                margin-left: 125px;
                line-height: 38px;
            }
        }
        .product__buy__btn{
            cursor: pointer;
            display: flex;
            margin-left: 52px;
            width: 210px;
            height: 50px;
            background-image: linear-gradient(90.0deg, #ff8500 0%, #ffae00 100%);
            font-size: 14px;
            line-height: 0;
            font-weight: 700;
            text-transform: uppercase;
            color: #ffffff;
            &:hover{
                background-image: linear-gradient(90.0deg, #d36e00 0%, #e59100 100%);
            }
            img{
                align-self: center;
                display: block;
                padding-left: 23px;
            }
            .product__buy__text{
                align-self: center;
                display: block;
                padding-left: 14px;
            }
        }
        .product__comparison__row{
            display: flex;
            .product__comparison{
                padding-right: 44px;
            }
            .product__comparison, .product__favourites{
                cursor: pointer;
                display: flex;
                img{
                  align-self: center;
                  padding-right: 5px;
                }
                p{
                  align-self: center;
                    font-size: 14px;
                    font-weight: 400;
                    text-decoration: underline;
                    color: #3b3b3b;
                }
            }
        }
        .product__info{
            display: flex;
            height: 225px;
            .product__info__icon{
                display: flex;
                margin-top: 18px;
                flex-direction: column;
                align-items: baseline;
                p{
                    font-size: 10px;
                    font-weight: 400;
                    text-transform: uppercase;
                    color: #91959a;
                    padding-bottom: 7px;
                    padding-left: 3px;
                }
                
            }
            .product__info__img{
                    margin-top: 18px;
                    margin-left: 31px;
                    img{
                        max-height: 225px !important;
                    }
            }
        }
     
    }
    .right__border--none{
        border-right: none;
    }
    .product__rating {
	display: inline-block;
	font-size: 0;
    }
    .product__rating span {
        padding: 0;
        font-size: 22px;
        line-height: 1;
        color: lightgrey;
    }
    .product__rating > span:before {
        content: '★';
    }
    .product__rating > span.active {
        color: #ff8600;
    }
</style>