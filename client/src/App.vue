<template>

  <div id="app" style="background-color:white; height: 100vh">

   <nav class="navbar">

      <div class="navbar-brand" >

        <a class="navbar-item" href="/" >
          <img src="./assets/img2bd.png">

          <img src="./assets/img21bd.png" id="rotate180">
        </a>
        <div class="navbar-menu">

          <div class="navbar-start">

            <router-link v-if="!$root.user" to="/" class="navbar-item ">

            </router-link>
          </div>
        </div>
        <div class="navbar-burger burger" data-target="navMenuTransparentExample">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div id="navMenuTransparentExample" class="navbar-menu">

          <div class="navbar-end" >


          <div class="navbar-item has-dropdown is-hoverable">

            <div class="navbar-link">
              Explorer
            </div>

            <div id="exploreDropdown" class="navbar-dropdown is-boxed">
              <!-- <a class="navbar-item " href="Master.vue"> -->
                <p>

                  <router-link  to="/browse" class="navbar-item">
                  <strong>BDs</strong>
                  </router-link>

                  <router-link  to="/browseArtists" class="navbar-item">
                  <strong>Auteurs</strong>
                  </router-link>

                  <router-link  to="/browsePublishers" class="navbar-item">

                  <strong>Editeurs</strong>
                  </router-link>
                </p>

            </div>

          </div>

            <div class="navbar-item has-dropdown is-hoverable">

            <div class="navbar-link">
              Contribuer
            </div>
            <div id="exploreDropdown" class="navbar-dropdown is-boxed">
              <!-- <a class="navbar-item " href="Master.vue"> -->
                <p>

                  <router-link  to="/add-master" class="navbar-item">
                  <strong>Ajouter une BD</strong>
                  </router-link>

                  <router-link  to="/add-release" class="navbar-item">
                  <strong>Ajouter une édition</strong>
                  </router-link>

                  <router-link  to="/add-series" class="navbar-item">
                  <strong>Ajouter une série</strong>
                  </router-link>

                  <router-link  to="/add-publisher" class="navbar-item">
                  <strong>Ajouter un éditeur</strong>
                  </router-link>

                  <router-link  to="/add-artist" class="navbar-item">
                  <strong>Ajouter un artiste</strong>
                  </router-link>
                </p>

            </div>


          </div>

          <router-link v-if="!$root.user" to="/add-master" class="navbar-item ">
            contribuez
          </router-link>

          <router-link v-if="!$root.user" to="/login" class="navbar-item ">
            Login
          </router-link>
          <router-link v-if="!$root.user" to="/signup" class="navbar-item ">
            Signup
          </router-link>
          <a class="navbar-item" @click.prevent="logout" v-if="$root.user" href="#">
            Logout
          </a>

        </div>
      </div>
    </nav>
    <router-view>Home</router-view>
    <footer id="footer">
    </footer>
  </div>
</template>

<script>
import { logout } from "@/api/auth";

export default {
  name: "app",
  methods: {
    logout() {
      logout(this.$root);
      this.$router.push("/");
    }
  }
};
</script>
<style>
@font-face {
  font-family: smilingCat;
  src: url(./assets/smiling_cat.otf);
}

#contain {
  font-style: oblique;
  font-family: smilingCat;
  font-weight: normal;
  color: black;
  font-size: 20px;
}

#footer {
  /*background-color:*/
  height: 15vh;
  width: 100px;
  /*background:url(./assets/bgimg1.png);*/
  /*position: fixed;*/
  bottom: 0;
}

#navMenuTransparentExample{
  font-style: oblique;
  font-family: smilingCat;
  font-weight: normal;
  color: white;
  font-size: 20px;
}
.container {
position: relative;
margin-top: 20px;
padding: 3%;
  max-width: 600px;
  border-style: solid;
  border-width: 0.5px;
  border-color: lightgrey;
  border-radius: 20px;
  opacity: 0.99;
  background-color: white
}
/*.navbaris-transparent {*/

.navcol {
  color: #00fdc8ff;
}

#bg-img {
  background-color: black;
  height: 15vh;
  width: 100%;
  /*background:url(./assets/bgimg1.png);*/
  position: fixed;
  bottom: 0;
}

#rotate180  {
  transform:          rotate(180deg);
-ms-transform:      rotate(180deg);
-moz-transform:     rotate(180deg);
-webkit-transform:  rotate(180deg);
max-height: 4rem;
}

.navbar-item img {
  max-height: 4rem;
}

#app form .label {
  font-style: oblique;
  font-family: smilingCat;
  font-weight: normal;
  color: black;
  font-size: 20px;
}


</style>
