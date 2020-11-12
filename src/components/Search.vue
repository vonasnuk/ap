<template>
    <div class="search__panel">
        <form>
            <input class="search__input" placeholder="Поиск по сайту" type="text">
            <select class="search__select">
                <option class="search__item" disabled selected>Все категории</option>
                <option class="search__item" value="select1">select1</option>
                <option class="search__item" value="select2">select2</option>
                <option class="search__item" value="select3">select3</option>
                <option class="search__item" value="select4">select4</option>
            </select>
            <div class="search__btn"><p>Поиск</p></div>
        </form>
    </div>
</template>

<style lang='scss' scoped>
    .search__panel{
        display: flex;
        height: 59px;
        width: 1015px;
        form{
         display: flex;
         margin-left: 20px;
         margin-top: 18px;
         .search__btn{
            width: 166px;
            height: 56px;
            background-color: #ff8900;
            cursor: pointer;
            p{
                color: #ffffff;
                font-size: 16px;
                font-weight: 700;
                text-transform: uppercase;
                color: #ffffff;
                text-align: center;
                margin-top: 18px;
            }
         }
        }
        .search__input{
            outline: none;
            border: none;
            padding-left: 28px;
            font-weight: 400;
            color: #929292;
            background-color: #f5f5f5;
            width: 671px;
            height: 56px;
            border-right: 1px solid #e4e4e4;
        }
        .search__select{
            cursor: pointer;
            border: none;
            width: 150px;
            height: 58px;
            font-size: 14px;
            line-height: 40px;
            font-weight: 400;
            color: #616161;
            background: url('../assets/select-icon.png') no-repeat right #f5f5f5;
            background-position-x: 116px;
            -webkit-appearance: none;
            -moz-appearance: none;
            -ms-appearance: none;
            appearance: none;
            outline: 0;
            padding-left: 14px;
            padding-right: 14px;
           
        }
    }

</style>