<template>
  <div id="app">
    <div class="nav-container">
      <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/impressum">Impressum</router-link>
      </nav>
    </div>
    <router-view/>
  </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Work+Sans&display=swap');
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&display=swap');

:root {
  --yellow-default: #DAB637;
  --yellow-tint-20: #F8F0D7;
  --yellow-tint-60: #E9D387;
  --yellow-shadow-20: #8B762A;
  --yellow-shadow-60: #3D361C;
  --white: #fff;
  --black-default: #000;
  --black-background: #161615;
  --black-default-20: #CCCCCC;
  --black-default-60: #666666;
  --black-default-80: #333333;
}

html {
  font-size: 16px;
}

html, body {
  font-family: 'Work Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 1rem;
  line-height: 160%;
  text-align: left;
  padding: 0;
  margin: 0;
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'DM Serif Display', Times, serif;
}

h1 {
  font-size: 6.854rem;
  line-height: 100%;
}

h2 {
  font-size: 4.236rem;
  line-height: 95%;
}

h3 {
  font-size: 2.618rem;
  line-height: 120%;
}

h4 {
  font-size: 1.618rem;
  line-height: 140%;
}

h5 {
  font-size: 1rem;
}

h6 {
  font-size: 1rem;
}

.nav-container {
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
}

.container {
  margin: 0 auto;
  width: 90%;
  position: relative;
}

nav {
  padding: 2rem 0rem;
  width: 90%;
  margin: 0 auto;
}

nav a {
  color: var(--white);
  text-decoration: none;
  font-size: 1.25rem;
  margin-right: 2rem;
}

nav a:last-of-type {
  margin-right: 0rem;
}

nav a.router-link-exact-active {
  color: var(--yellow-default);
}
</style>
