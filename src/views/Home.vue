<template>
  <div class="main-page">
    <TopNav></TopNav>
    <div class="main">
        <div  class="some-page-wrapper">
            <div class="row">
                <div class="column">
                    <div class="left-column">
                        <img src="../assets/images/skate.png" alt="">
                        <h3 v-bind:class="{changeColor: isBgChanged}" class="first-text">SPEEDY </h3>
                        <h3 v-bind:class="{changeColor: isBgChanged}" class="second-text">QUADS</h3>
                    </div>
                </div>
                <div class="column">
                    <div class="right-column">
                        <form action="">
                            <div class="product">
                                <div class="product-title">
                                    <p v-bind:class="{changeColor: isBgChanged}">Smart Speedy quads</p>
                                </div>
                                <div class="product-rating">
                                    <span class="fa fa-star checked"></span>
                                    <span class="fa fa-star checked"></span>
                                    <span class="fa fa-star checked"></span>
                                    <span class="fa fa-star"></span>
                                    <span class="fa fa-star"></span>
                                </div>
                            </div>
                            <h6 v-bind:class="{changeColor: isBgChanged}">Productcode:8494930</h6>
                            <p v-bind:class="{changeColor: isBgChanged}" class="product-price">3500 py6</p>
                            <div class="product-description">
                                <p v-bind:class="{changeColor: isBgChanged}" >Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi totam deserunt veniam dolore. 
                                    Laudantium recusandae et, autem numquam fugiat perferendis placeat illo minima rem aspernatur, 
                                    eligendi iure iusto a expedita placeat illo minima rem aspernatur, 
                                    eligendi iure iusto a expedita.</p>
                                <a href="#" v-bind:class="{changeColor: isBgChanged}">see more</a>
                            </div>
                            <div class="product-color">
                                <p v-bind:class="{changeColor: isBgChanged}">Colors:</p>
                                <div class="product-color_circles">
                                    <button class="dot dot1" v-on:click.prevent="changebgColor1()"></button>
                                    <button class="dot dot2" v-on:click.prevent="changebgColor2()"></button>
                                    <button class="dot dot3" v-on:click.prevent="changebgColor3()"></button>
                                    <button class="dot dot4" v-on:click.prevent="changebgColor4()"></button>
                                </div>
                            </div>
                            <div class="product-types">
                                <p v-bind:class="{changeColor: isBgChanged}">Types:</p>
                                <select name="types" v-bind:class="{changeSelect: isBgChanged || isGrey}">
                                    <option value="volvo">Type 1</option>
                                    <option value="saab">Type 2</option>
                                    <option value="opel">Type 3</option>
                                    <option value="audi">Type 4</option>
                                </select>
                            </div>
                            <a href="#" class="button">Order now</a>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>

import TopNav from '../components/navs/HomeNav.vue'
export default {
  name: 'Home',
  components: {
    TopNav
  },
  props: {
    msg: String
  },
  data () {
    return {
      selectedColor: '#0392BF',
      yellow: '#FBEC06',
      grey: "#B3D4E0",
      rose: '#ED48BA',
      mainColor: '#0392BF',
      isBgChanged: false,
      colorPanelBorder: '',
      marginLeft: ''
    }
  },
  methods: {
      changebgColor1(){
          this.selectedColor = this.mainColor
          this.isBgChanged = false;
          // this.colorPanelBorder = '2px solid #fff';
      },
      changebgColor2(){
          this.selectedColor = this.rose;
          this.isBgChanged = false;
          // this.colorPanelBorder = '2px solid #fff';
      },
      changebgColor3(){
          this.selectedColor =this.yellow;
          this.isBgChanged= true;
      //    this.colorPanelBorder = '2px solid #fff';
      },
      changebgColor4(){
          this.selectedColor = this.grey
          this.isBgChanged = true;
      },

      
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.main-page{
    color: #B3D4E0;
    font-weight: 'Jost', sans-serif;
    font-weight: 300;
    background-color:  #0392BF ;
    font-size: 20px;
    text-rendering: optimizeLegibility;
}
.main{
    height: 100vh;
}
.some-page-wrapper{
    margin-top: 60px;

}

.row {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    width: 100%;
}

.column {
    display: flex;
    flex-direction: column;
    flex-basis: 100%;
    flex: 1;
}

.left-column{
    position: relative;
    text-align: center;    
    margin-top: 30px;
    margin-bottom: 40px;

}

.left-column img{
    height: 400px;
    width: auto;
}

.left-column h3{
    position: absolute;
    font-size: 300%;
    color: #dbdbdb;
    font-weight: 600;
    font-family: 'Jost', sans-serif;
}

.first-text{
    top: 80%;
    left: 25%;
}

.second-text{
    top: 95%;
    left: 34%;
}

.right-column{
    font-family: 'Jost', sans-serif;
    color: #dbdbdb;
    width: 70%;
    margin-left: 80px;
}

.right-column h6{
    font-weight: normal;
    color: #B3D4E0;
}

.main-title{
    text-transform: uppercase;
}

.product {
    display: flex;
    align-items: center;
    flex-direction: row;
    align-items: center;
    margin-bottom: 10px;
}

.product-title {
    font-size: 130%;
    margin-right: 20px;
    text-transform: uppercase;
}

.product-rating .fa{
    font-size: 15px;
    color: #FBEC06;
}

.product-price{
    font-size: 120%;
    font-weight: bold;
    margin: 10px 0;
}

.product-description p{
    font-weight: normal;
    font-size: 70%;
    color: #cccccc;
    margin-bottom: 5px;
}

.product-description a{
    color: #B3D4E0;
}

.product-color{
    margin-top: 40px;
    display: flex;
    flex-direction: row;
    align-items: center;
}

.product-color p{
    font-size: 100%;
    margin-right: 30px;
    text-transform: uppercase;
}

.dot{
    height: 30px;
    width: 30px;
    background-color: #bbb;
    border-radius: 50%;
    margin-right: 10px;
    display: inline-block;
}
.dot1{
    background-color: #52d4fc;
}
.dot2{
    background-color: #ED48BA;
}
.dot3{
    background-color: #FBEC06;
}
.dot4{
   background-color: #B3D4E0;
}

.product-color_cirles button:active{
  border: 2px solid #fff;
}

.product-types{
    margin: 20px 0 40px 0;
    display: flex;
    flex-direction: row;
    align-items: center;
}

.product-types p{
    font-size: 100%;
    margin-right: 30px;
    text-transform: uppercase;
}

.product-types select{
    background-color: transparent;
    width: 150px;
    height: 35px;
    border-color: #B3D4E0;
    color: #B3D4E0;
}
.product-types .changeSelect{
    background-color: transparent;
    width: 150px;
    height: 35px;
    border-color: black !important;
    color: black !important;
}

.button {
    background-color: #ED48BA;
    border: none;
    color: white;
    padding: 10px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
  }


.fa {    
    color: #61b3ff;
}

.background {
    background-color: #0392BF;
  }
  
  .pink {
    background-color: #ED48BA;
  }
  
  .yellow {
    background-color: #FBEC06;
    height: 100% !important;
  }
  
  .grey {
    background-color: #B3D4E0;
  }
  
  @media only screen and (max-width: 800px) {
    
    .right-column{
        margin-top: 50px;
        margin-bottom: 50px;
    }

    main{
        height: 100%;
        margin-left: 0px;
    }
  }

  @media screen and (max-width: 600px) {
    .main-nav{
        margin-left: 20px;
    }
    .main-nav li{display: none;}
    .main-nav a.icon {
      float: right;
      display: block;
    }
  }

</style>
