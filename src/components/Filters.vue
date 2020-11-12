<template>
    <div>
        <div class="filters-block">
            <div class="filters__tabs">
                <div class="filter__link">
                    <img class="filter__img" src="../assets/car.svg" alt="">
                    <p>Ссылка 1</p>
                </div>
                <div class="filter__link">
                    <img class="filter__img" src="../assets/furgon.svg" alt="">
                    <p>Ссылка 2</p>
                </div>
                <div class="filter__link">
                    <img class="filter__img" src="../assets/wheel.svg" alt="">
                    <p>Ссылка 3</p>
                </div>
                <div class="filter__link">
                    <img class="filter__img" src="../assets/oil.svg" alt="">
                    <p>Ссылка 4</p>
                </div>
                <div class="filter__link">
                    <img class="filter__img" src="../assets/car.svg" alt="">
                    <p>Ссылка 5</p>
                </div>
            </div>
            <div class="filters__options">
                <div class="filters__toggle">
                    <div class="filters__tabs__btn" 
                        :class="{filters__tabs__btn__active: !filerToggle}"
                        v-on:click='toggleFilter'>Tab 1</div>
                    <div class="filters__tabs__btn" 
                        :class="{filters__tabs__btn__active: filerToggle}"
                        v-on:click='toggleFilter'>Tab 2</div>
                </div>
                <div class="filters__panel" :class="{filters__panel__toggle: !filerToggle}">
                    <form class="filters__form" ref="form__tab__first">
                        <select class="filter__select">
                            <option class="filter__item" value="select1">Select 1</option>
                            <option class="filter__item" value="select2">Select 2</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select 1</option>
                            <option class="filter__item" value="select4">Select 3</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select 1</option>
                            <option class="filter__item" value="select4">Select 4</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select 1</option>
                            <option class="filter__item" value="select4">Select 5</option>
                        </select>
                        <select class="filter__select filter__select-row">
                            <option class="filter__item" value="select3">Select 1</option>
                            <option class="filter__item" value="select4">Select 7</option>
                        </select>
                        <div class="filters__form__text">Цена</div>
                        <input class="" type="number">
                        <input class="" type="number">
                    </form>
                    <div class="filter__btn">
                        <div class="filter__btn--clear" v-on:click="resetForm">
                            X Очистить фильтр
                        </div>
                        <div class="filters__form--used">
                            Применить фильтр
                        </div>
                    </div>
                </div>
                <div class="filters__panel" :class="{filters__panel__toggle: filerToggle}">
                    <form class="filters__form" ref="form__tab__second">
                        <select class="filter__select">
                            <option class="filter__item" value="select1">Select</option>
                            <option class="filter__item" value="select2">Select 2</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select</option>
                            <option class="filter__item" value="select4">Select 3</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select</option>
                            <option class="filter__item" value="select4">Select 4</option>
                        </select>
                        <select class="filter__select">
                            <option class="filter__item" value="select3">Select</option>
                            <option class="filter__item" value="select4">Select 5</option>
                        </select>
                        <select class="filter__select filter__select-row">
                            <option class="filter__item" value="select3">Select</option>
                            <option class="filter__item" value="select4">Select 7</option>
                        </select>
                        <div class="filters__form__text">Цена</div>
                        <input class="number__input" type="number" onkeypress="return event.charCode >= 48" min="1">
                        <input class="number__input" type="number" onkeypress="return event.charCode >= 48" min="1">
                    </form>
                    <div class="filter__btn">
                        <div class="filter__btn--clear" v-on:click="resetForm">
                            X Очистить фильтр
                        </div>
                        <div class="filters__form--used">
                            Применить фильтр
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                filerToggle: false
            }
        },
        methods:{
            toggleFilter(){
                this.filerToggle = !this.filerToggle
            },
            resetForm(){
                this.$refs.form__tab__first.reset();
                this.$refs.form__tab__second.reset();
            }
        }
    }
</script>

<style lang="scss" scoped>
    .filters-block{
        margin-left: 20px;
        margin-top: 37px;
        width: 1015px;
        height: 374px;
        background-color: #696969;
        z-index: 1;
        .filters__tabs{
            display: flex;
            justify-content: space-evenly;
            background-color: #606a76;
            height: 74px;
            .filter__link{
                cursor: pointer;
                display: flex;
                align-self: center;
                height: 64px;
                width: 183px;
                font-size: 18px;
                font-weight: 700;
                color: #ffffff;
                padding-top: 8px;
                border-bottom: 2px solid #606a76;
                opacity: 0.4;
                &:hover{
                    border-bottom: 2px solid #ffc925;
                    opacity: 1;
                }
                .filter__img{
                    opacity: 1;
                }
                p{
                    margin-left: 13px;
                }

            }
        }
        .filters__options{
            background-color: #696969;
            padding-left: 16px;
            padding-top: 24px;
            .filters__toggle{
                background-color: #ffffff;
                display: flex;
                margin-left: 20px;
                width: 281px;
                height: 44px;
                .filters__tabs__btn{
                    cursor: pointer;
                    border: 3px solid #ffffff;
                    width: 50%;
                    padding-top: 12px;
                    text-align: center;
                    font-size: 14px;
                    font-weight: 400;
                    color: #ffffff;
                    background-color: #ff8900;
                    

                }
                .filters__tabs__btn__active{
                    color: #696969;
                    background-color: #ffffff;
                }
            }
            .filters__panel{
                padding-top: 22px;
                padding-left: 18px;
                .filters__form{
                    display: flex;
                    flex-wrap: wrap;
                    input{
                        cursor: pointer;
                        width: 68px;
                        height: 37px;
                        margin-right: 11px;
                        margin-top: 27px;
                    }
                    input::-webkit-outer-spin-button,
                    input::-webkit-inner-spin-button {
                        -webkit-appearance: none;
                    }
                    .filters__form__text{
                        font-size: 14px;
                        font-weight: 400;
                        color: #ffffff;
                        padding-top: 37px;
                        padding-left: 3px;
                        margin-right: 25px;
                    }
                    .number__input:focus{
                        border-bottom: 1px solid #ff8500;
                    }
                }
                .filter__select{
                    cursor: pointer;
                    border: none;
                    width: 222px;
                    height: 40px;
                    font-size: 14px;
                    font-weight: 400;
                    color: #9c9c9c;
                    background: url('../assets/select-filter-icon.png') no-repeat right #ffffff;
                    background-position-x: 191px;
                    -webkit-appearance: none;
                    -moz-appearance: none;
                    -ms-appearance: none;
                    appearance: none;
                    outline: 0;
                    border-bottom: 1px solid #696969;
                    margin-right: 20px;
                    padding-left: 15px;
                    .filter__item{
                        font-size: 14px;
                        line-height: 40px;
                        font-weight: 400;
                        color: #9c9c9c;
                    }
                }
                .filter__select-row{
                    margin-top: 28px;
                    margin-left: 242px;
                }
                .filter__btn{
                    display: flex;
                    margin-top: 20px;
                    justify-content: space-between;
                    .filter__btn--clear{
                        cursor: pointer;
                        line-height: 53px;
                        text-align: center;
                        width: 210px;
                        height: 50px;
                        background-color: #ff4800;
                        font-size: 14px;
                        font-weight: 400;
                        margin-left: 5px;
                        color: #ffffff;
                    }
                    .filters__form--used{
                        cursor: pointer;
                        line-height: 53px;
                        margin-right: 34px;
                        width: 210px;
                        height: 50px;
                        background-image: linear-gradient(90.0deg, #ff8500 0%, #ffae00 100%);
                        font-size: 14px;
                        font-weight: 700;
                        text-transform: uppercase;
                        color: #ffffff;
                        text-align: center;
                    }
                }
                
            }
            
        }
        .filters__panel__toggle{
            display: none;
        }
    }
</style>