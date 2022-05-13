<template>
  <nav>
    <div>
      <i class="fa-solid fa-badge-check">TODO</i>
    </div>
  </nav>
  <router-view />
  <footer>Copyright @ The ToDo List 2022. All rights reserved.</footer>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav {
  padding: 10px;
  background-color: rgba(27, 27, 27, 1.5);
}

.fa-badge-check {
  font-weight: bold;
  color: white;
}

nav a.exact-active {
  color: #ffffff;
}
nav a:hover {
  transform: scale(1.1);
}

footer {
  padding: 10px;
  background-color: rgba(50, 50, 50, 0.5);
}
</style>
