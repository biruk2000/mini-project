<template>
    <div class="sidebar" :class="{sidenav: sidenavhidden}">
        <div class="logo-content">
            <div class="logo">
                <div class="logo-inner">
                    <div class="logo-inner-element under-pos"></div>
                    <div class="logo-inner-element center-pos"></div>
                    <div class="logo-inner-element top-pos"></div>
                </div>
            </div>
        </div>
        <div class="nav-icons">
            <a href="#"><i class='bx bxs-home bx-sm'></i></a>
            <a href="#"><i class='bx bxl-blogger bx-sm'></i></a>
            <a href="#"><i class='bx bxs-shopping-bags bx-sm'></i></a>
            <a href="#"><i class='bx bxs-info-circle bx-sm'></i></a>
            <!-- <a href="#"><i class='bx bx-log-in bx-sm'></i></a> -->
        </div>
        <div class="media">
            <ul>
                <li><a href="http://www.facebook.com"><box-icon class="social-bx" type='logo' name='facebook'></box-icon></a></li>
                <li><a href="http://www.instagram.com"><box-icon type='logo' name='instagram'></box-icon></a></li>
                <li><a href="http://www.vector.com"><i class="fa fa-google-wallet"></i></a></li>
            </ul>
            <br>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Sidenav', 
    data (){
        return {
            // sidenavhidden: false,
        }
    },
    

}
</script>

<style scoped>
    .sidebar {
        position: fixed;
        left: 0;
        width: 100px;
        height: 100%;
        padding-top: 30px;
        z-index: 1;
        background-color: #B3D4E0;   
    }

    .sidebar .media {
        position: absolute;
        bottom: 70px;
        left: 50%;
        transform:translateX(-50%);
        display: flex;
    }

    .sidebar .media ul li {
        padding: 10px;

    }

    .sidebar .nav-icons{
        display: none;
    }

    .sidebar .nav-icons a i.bx{
        /* width: 100px !important; */
        height: 100px !important;
        color: #61b3ff !important;

    }

    .media ul li a {    
       color: #61b3ff !important;
    }

    .logo-content {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    .logo {
        background-color: #ED48BA;
        height: 60px;
        width: 60px;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
    .logo-inner {
        border: 4px solid #fff;
        height: 35px;
        width: 35px;
        border-radius: 50%;
        position: absolute;
        display: flex;
        justify-content: space-between;
    }
    
    .logo-inner-element {
        background-color: #fff;
        content: "";
        width: 10px;
        height: 10px;
        border-radius: 50%;
    }
    
    .center-pos {
        position: relative;
        top: 13px;
    }
    
    .top-pos {
        position: relative;
        top: -4px;
    }
    
    .under-pos {
        position: relative;
        top: 10px;
        left: -7px;
    }

     @media screen and (max-width: 600px) {

    .sidebar{ 
        display: none;
    }

    .sidenav{
        display: block;
        width: 12%;
    }

    .sidebar .nav-icons{
        display: flex;
        flex-direction: column;
        /* justify-content: center; */
        align-items: center;
        margin-top: 50px;
        max-height: 50px;
    }

    .sidebar.media{
       position: absolute;
       bottom: 0px;
    }
  }
</style>
