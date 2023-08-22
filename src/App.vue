<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TopNav from './components/TopNav.vue'
import VideoPlayer from './components/VideoPlayer.vue';
</script>

<template>
  <header class="header">
    
    <img class="avatar" height="150px" src="./assets/dan.jpeg" alt="Photo of Daniel Allen" />
    
    <div class="wrapper">
      <TopNav msg="PORTFOLIO DANIEL ALLEN 2023" />
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/portfolio">Portfolio</RouterLink>
      </nav>
    </div>
    
  </header>
  
  <body>
    <div class="video">
    <VideoPlayer class="router-view-cyan"/>
    </div>
    <div class="view-container">
    <!-- This is the encasing div for the router view -->
    <RouterView  />
    </div>
    
  </body>

</template>

<style scoped>
.router-view-cyan {
  background-color: cyan; /* Set the background color to cyan */
}

.view-container {
  width: 80%;
  margin-top: 5rem;
  margin-left: 5rem;
  padding: 1.5em;
  box-sizing: border-box;

} 
.avatar {
  height: 150px;
  border: 1px solid rgba(255, 255, 255, 0.4);
  border-radius: 30%;
  margin: 0 30px;
}
header {
  line-height: 1.3;
  max-height: 100vh;
}


/* This is indicating the active link in the nav bar */
nav a.router-link-exact-active {
  color: rgb(72, 171, 242);
}
/* Color and text are css variables that are defined in the global css files */

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  color: white;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}



nav a:first-of-type {
  border: 0;
}


@media (min-width: 500px) {
  header {
    display: flex;
    place-items: center;
  }


  .video {
  width: 100%;
  height: 250px;
  margin-top: 15rem;
  }
  
  .header {
  width: 100%; /* Span the width of the page */
  background-color: #333; /* Set your desired background color */
  color: #fff; /* Set your desired text color */
  position: fixed; /* Keep the header fixed at the top */
  top: 0; /* Position it at the top */
  padding: 10px 0; /* Add padding as needed */
  left: 0; /* Horizontally align to the left */
  z-index: 999; /* Make the header appear on top */
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
}



</style>
