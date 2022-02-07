<template>
    <header>
        <Sidenav />

        <nav>
            <div class="nav">
                <ul class="main-nav" id="my-nav" v-bind:class="{changeNav: isBgChanged}">
                    <li><router-link to="/">Home</router-link></li>
                    <li><router-link to="#">Blog</router-link></li>
                    <li><router-link to="#">Shop</router-link></li>
                    <li><router-link to="#">About</router-link></li>
                    <li><router-link to="#">Login</router-link></li>
                    <a href="/" class="icon" v-on:click.prevent="toggleNav" :style="{marginLeft: marginLeft}">
                        <i class="fa fa-bars"></i>
                        </a>
                </ul>
                <div class="cart">
                   <router-link to="/cart" style="text-decoration: none; color: #fff"><i v-bind:class="{changeNav: isBgChanged}" class="fa fa-shopping-cart" aria-hidden="true"></i></router-link> 
                </div>
            </div>
        </nav>   
    </header>
</template>

<script>
import Sidenav from './HomeSideNav.vue';

export default {
    name: 'Topnav',
    components: {
        Sidenav
    },
    methods: {
        toggleNav: function () {
          if (this.sidenavhidden == false) {
              this.sidenavhidden = true;
              this.marginLeft = '60px';
          }else{
              this.sidenavhidden = false;
              this.marginLeft = '';
          }
        console.log(this.sidenavhidden)
      }
    }
}
</script>



<style scoped>
    .nav {
        display: flex;
        margin-left: 20px;
        margin-right: 50px;
        align-items: center;
        justify-content: space-between;
    }

    .changeNav li a{
        color: black !important;
    }

    .changeNav .cart .fa{
        color: black !important;
    }

    .cart{
        margin-top: 40px; 
        margin-right: 20px;
    }
    .cart i{
        height: 40px;
        width: auto;
        float: right;
        color: #fff;
    }

    .main-nav{
        float: left;
        list-style: none;
        margin-top: 30px;
        margin-left: 100px;
        display: flex;
    }

    .main-nav li{
        margin-left: 30px;
    }

    .main-nav .icon{
        display: none;
    }

    .main-nav .icon i{
        color: white;
    }

    .main-nav li a:link,
    .main-nav li a:visited{
        padding: 4px 0;
        color: #dbdbdb;
        text-decoration: none;
        font-size: 80%;
        border-bottom: 2px solid transparent;
        transition: border-bottom .2;
    }

    .main-nav li a:hover,
    .main-nav li a:active{
        border-bottom: 2px solid;
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

