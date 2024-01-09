<template>
  <header id="header" class="isTransparent border-bottom border-black">
  
  <nav class="navbar navbar-expand-lg px-3 pt-0">
    <div class="collapse navbar-collapse row w-75" id="navbarText">
        <div class="col-8">
          <div class="me-4 pb-3 pt-1 ms-3 headerText fw-bolder">
            <span class="me-5">208-939-0748</span>
            <span>Monday - Saturday 9 AM to 7 PM</span>
          </div>
        <ul class="navbar-nav d-flex justify-content-start">
          <li>
            <router-link :to="{ name: 'Home' }" class="btn headerText fw-bolder selectable text-uppercase">
              Home
            </router-link>
          </li>
          <li>
            <router-link :to="{ name: 'Menu' }" class="btn headerText fw-bolder selectable text-uppercase">
              Menu
            </router-link>
          </li>
          <li>
            <a @click="goToContact('contact')" class="btn headerText fw-bolder selectable text-uppercase">
              Contact
            </a>
          </li>
          <li>
            <a class="btn headerText fw-bolder selectable text-uppercase" target="_blank" href="https://www.clover.com/online-ordering/bowl-of-heaven-eagle-eagle">Order Online</a>
          </li>
        </ul>
        </div>
      </div>
    
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarText"
      aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    
    
    <router-link class="navbar-brand d-flex p-0 pb-1" :to="{ name: 'Home' }">
            <div class="d-flex flex-column align-items-center">
              <img id="mainLogo" alt="logo" :src="route.fullPath === '/' ? '../src/assets/img/Logo/White/Web/bowl-of-heaven---monocolor-logo-white-rgb.svg' : '../src/assets/img/Logo/Black/Web/bowl-of-heaven---monocolor-logo-black-rgb.svg' " height="65" />
            </div>
      </router-link>
  </nav>
</header>
  
</template>

<script>
import { useRoute, useRouter } from 'vue-router';
import { logger } from '../utils/Logger';
export default {

  mounted() {
    // Add a scroll event listener
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    // Remove the scroll event listener when the component is destroyed
    window.removeEventListener('scroll', this.handleScroll);
  },
  setup() {
    const route = useRoute( )
    const router = useRouter( )

    return {
      isTransparent: true,
      route,
      scrollThreshold: false,
      isHomePage: route.fullPath == '/',
      handleScroll() {
        // this.isTransparent = window.scrollY < scrollThreshold;
        let elements = document.getElementsByClassName('headerText');
        let navbar = document.getElementById('header')
        if (window.scrollY > 300 || route.fullPath !== '/') {
          document.getElementById('mainLogo').setAttribute('src', '../src/assets/img/Logo/Black/Web/bowl-of-heaven---monocolor-logo-black-rgb.svg')
          for (let i = 0; i < elements.length; i++) {
            elements[i].style.color = 'black';
          }
          navbar.style.backgroundColor = '#fffaf3'
        } else {
          document.getElementById('mainLogo').setAttribute('src', '../src/assets/img/Logo/White/Web/bowl-of-heaven---monocolor-logo-white-rgb.svg')
          for (let i = 0; i < elements.length; i++) {
            elements[i].style.color = 'white';
          }
          navbar.style.backgroundColor = 'transparent'
        }
      },

      async goToContact(param) {
        if(!param){return}
        await router.push({
          name: "Home",
        })
        document.getElementById("contact").scrollIntoView()
      }
    }
  },
}
</script>

<style scoped>
a:hover {
  text-decoration: none;
}



.topper {
  transform: translateY(-2.25rem) translateX(-64.5rem)
}

/*--------------------------------------------------------------
# Header
--------------------------------------------------------------*/


#header {
  transition: all 0.5s;
  padding: 10px 0;
}

.isTransparent {
  background-color: transparent;
}

#header.header-scrolled {
  top: 0;
  /* background: #ECE6BD; */
}

#header .logo h1 {
  font-size: 28px;
  margin: 0;
  line-height: 1;
  font-weight: 400;
  letter-spacing: 3px;
}

#header .logo h1 a,
#header .logo h1 a:hover {
  color: #fff;
  text-decoration: none;
}

#header .logo img {
  padding: 0;
  margin: 0;
  max-height: 40px;
}

</style>
