<template>
  <div>
    <nav class="navbar">
      <div class="logo">
        <a href="/">
          <img src="@\assets\logo.svg" alt="Logo" />
        </a>
      </div>

      <ul class="nav-links">
        <li v-for="(item, index) in navItems" :key="index">
          <a :href="item.link">{{ item.text }}</a>
        </li>
      </ul>

      <div class="search">
        <div class="input-with-button">
          <input type="text" placeholder="Buscar..." />
          <button type="button">Botão</button>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "NavigationBar",
  data() {
    return {
      navItems: [
        { text: "Filmes", link: "/filmes" },
        { text: "Séries", link: "/series" },
        { text: "Trailers", link: "/trailers" },
        { text: "Notícias", link: "/noticias" },
      ],
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');

.navbar {
  background-color: #000020;
  padding: 10px 20px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
} 

.logo {
  margin-right: 50px;
}

.search {
  display: flex;
  align-items: center;
  margin-left: 50px;
}

.search input[type="text"] {
  padding: 5px;
  border: 2px solid #6a1b9a;
  border-radius: 100px;
  font-size: 12px;
  outline: none;
  font-family: 'Inter', sans-serif;
}

.search button {
  padding: 5px;
  background-image: url("@/assets/lupa.svg");
  border: none;
  font-size: 12px;
  background-color: transparent;
  text-indent: -9999px;
  width: 20px; 
  height: 30px;
  background-repeat: no-repeat;
}

.input-with-button {
  position: relative;
}

.input-with-button button {
  position: absolute;
  top: 9px;
  right: 0;
  height: 1px;
}

.nav-links {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.nav-links li {
  font-family: 'Inter', sans-serif;
  margin-right: 20px;
}

.nav-links li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.nav-links li a:hover {
  color: #6a1b9a;
}
</style>
