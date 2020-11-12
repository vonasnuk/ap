<template>
  <div>
    <Navbar />
    <Header :counter="counter" />
    <div class="content">
      <Sidebar />
      <div>
        <Search />
        <Filters />
      </div>
    </div>
    <Products @updateCount='updateCount' />
    <router-view/>
    <Footer />
  </div>
</template>



<script>
  import Navbar from '../src/components/Navbar'
  import Header from '../src/components/Header'
  import Sidebar from '../src/components/Sidebar'
  import Search from '../src/components/Search'
  import Filters from '../src/components/Filters'
  import Products from '../src/components/Products'
  import Footer from '../src/components/Footer'

  export default {
    data(){
      return{
        counter: {
          counterComparison: 0,
          counterFavorites: 0,
          counterBasket: 0
        }
        
      }
    },
    components:{
      Navbar,
      Header,
      Sidebar,
      Search,
      Filters,
      Products,
      Footer
    },
    methods:{
      updateCount(data){
        this.counter.counterComparison = data.counterComparison
        this.counter.counterFavorites = data.counterFavorites
        this.counter.counterBasket = data.counterBasket
      }
    }
  }
</script>

<style lang="scss">
  body{
    margin: 0;
  }
  *{
    font-family: 'Roboto', sans-serif;
  }
  button{
    &:focus, &:active{
        outline: none;
    }
  }
  input{
    &:focus, &:active{
        outline: none;
    }
  }
  .content{
    display: flex;
  }
</style>
