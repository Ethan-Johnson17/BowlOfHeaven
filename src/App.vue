<template>
  <header>
    <Navbar />
  </header>
  <main>
    <router-view />
  </main>
   <footer id="footer">
      <div class="container-fluid text-dark border-top border-black pt-3">
        <h3>Bowl of Heaven</h3>
        <p class="fw-bold text-danger">
          ---------------------- BOH Mission ----------------------------
        </p>
        <div class="social-links">
          <!-- <a href="#" class="twitter"><i class="mdi mdi-twitter"></i></a> -->
          <a href="https://www.facebook.com/profile.php?id=100063695134558" class="facebook"><i class="mdi mdi-facebook fs-2"></i></a>
          <a href="https://instagram.com/bowlofheaveneagle?igshid=OGQ5ZDc2ODk2ZA==" class="instagram"><i class="mdi mdi-instagram fs-2"></i></a>
          <!-- <a href="#" class="google-plus"><i class="mdi mdi-skype"></i></a>
          <a href="#" class="linkedin"><i class="mdi mdi-linkedin"></i></a> -->
        </div>
        <div class="copyright">
          &copy; Copyright {{ year }} <strong><span>Bowl of Heaven Eagle LLC</span></strong
          >. All Rights Reserved.
        </div>
      </div>
    </footer>
</template>

<script>
import { computed } from 'vue'
import { AppState } from './AppState'
import Navbar from './components/Navbar.vue'

export default {
  setup() {
    return {
      appState: computed(() => AppState),
      year: new Date().getFullYear()
    }
  },
  components: { Navbar }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";

:root{
  --main-height: calc(100vh - 32px - 64px);
}


// footer {
//   display: grid;
//   place-content: center;
//   height: 32px;
// }

#footer {
  font-size: 14px;
  text-align: center;
  padding: 30px 0;
  background-color: #fffaf3;
}

#footer h3 {
  font-size: 36px;
  font-weight: 700;
  color: var(--lightpink);
  position: relative;
  padding: 0;
  margin: 0 0 15px 0;
}

#footer p {
  font-size: 15;
  font-style: italic;
  padding: 0;
  margin: 0 0 40px 0;
}

#footer .social-links {
  margin: 0 0 40px 0;
}

#footer .social-links a {
  font-size: 18px;
  display: inline-block;
  background: var(--lightOrange);
  color: var(--darkOrange);
  line-height: 1;
  padding: 8px 0;
  margin-right: 4px;
  text-align: center;
  width: 46px;
  height: 28px;
    /* Half of the width to create a semi-circle */
  border-radius: 0 0 50% 50%;
    /* Applying border-radius to create a semi-circle effect */
  transition: 0.3s;
}

#footer .social-links a:hover {
  background: var(--darkOrange);
  color: var(--lightOrange);
}

#footer .copyright {
  margin: 0 0 5px 0;
}

#footer .credits {
  font-size: 13px;
}

.bx {
  transform: translateY(-5px);
  font-size: 24px;
}

main {
  flex-grow: 1;
  // margin-top: 50rem;
}

header {
    position: sticky;
    top: 0;
    z-index: 1000;
}
</style>
