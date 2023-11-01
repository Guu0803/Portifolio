<template>
  <div class="window">
    <div class="header">
      <div class="header-name">
        Gustavo
        <div style="color: var(--red);">
          Nogueira
        </div>
      </div>
      <div class="nav-links">
        <div v-on:click="index('0')">
          Home
        </div>
        <div v-on:click="index('1')">
          Sobre
        </div>
        <div v-on:click="index('2')">
          Skills
        </div>
        <div v-on:click="index('3')">
          Projetos
        </div>
      </div>
      <button>
        <a href="https://www.linkedin.com/in/gustavo-henrique-nogueira-deranzani-bicudo-11659a221/">
          Contato
        </a>
      </button>
    </div>
    <div class="row-container" id="container">
      <div class="presentation-container" id="presentation">
        <div class="presentation">
          <div class="greeting">
            Olá, eu sou <div>
              Gustavo Nogueira
            </div>
            <div>
              um Front-End Developer apaixonado por criar experiências incríveis na web.
            </div>
          </div>
          <div class="presentation-inks">
            <div class="link">
              <a href="https://www.linkedin.com/in/gustavo-henrique-nogueira-deranzani-bicudo-11659a221/"> <img
                  src="@/assets/linkedin.png"> </a>
            </div>
            <div class="link">
              <a href="https://github.com/Guu0803"> <img src="@/assets/github.png"> </a>
            </div>
          </div>
        </div>
        <img src="@/assets/coding.svg" class="presentation-img">
      </div>

      <div class="about-me-container" id="about">
        <div class="title-about">
          Sobre Mim
        </div>
        <div>
          <img src="@/assets/foto.jpeg" class="photo">
          <div class="about-me">
            Sou formado em Engenharia Civil, e após o término da faculdade meu fascínio por tecnologia me levou a fazer
            uma
            transição empolgante para o desenvolvimento front-end. Estou comprometido em combinar minha mentalidade
            analítica de engenheiro com habilidades criativas para criar soluções digitais incríveis.
            Desde que mergulhei no mundo da programação, há um pouco mais de 1 ano, minha jornada tem sido emocionante e
            desafiadora. Desde então, com sede de aprendizado venho constantemente explorando novas tecnologias,
            aprimorando
            minhas habilidades e buscando maneiras de aprimorar a web para todos.
          </div>
        </div>
      </div>

      <div class="skills" id="skill">
        Minhas principais skills
        <div>
          <div>
            <img src="@/assets/html-icon.png" class="skill-icon">
            HTML
          </div>
          <div>
            <img src="@/assets/css-icon.png" class="skill-icon">
            CSS
          </div>
          <div>
            <img src="@/assets/javascript-icon.png" class="skill-icon">
            JavaScript
          </div>
          <div>
            <img src="@/assets/vue-icon.png" class="skill-icon">
            Vue.js
          </div>
          <div>
            <img src="@/assets/git-icon.png" class="skill-icon">
            Git
          </div>
          <div>
            <img src="@/assets/github-icon.png" class="skill-icon">
            GitHub
          </div>
        </div>
      </div>

      <div class="projects" id="project">
        Alguns dos projetos que já realizei
        <div class="my-projects">
          <div v-on:mouseover="showDescription('spotify')" v-on:mouseleave="hideDescription('spotify')">
            <img src="@/assets/spotify.png" class="project-img">
            <div class="description" id="spotify">
              <div class="title-description">
                Spotify
                <span class="material-icons open-in">
                  open_in_new
                </span>
              </div>
              Este projeto é um clone do aplicativo de desktop do Spotify, uma das plataformas mais populares de streaming
              de música do mundo. O objetivo era recriar o design do app do Spotify para a web.
            </div>
          </div>
          <div v-on:mouseover="showDescription('space')" v-on:mouseleave="hideDescription('space')">
            <img src="@/assets/spaceflix.png" class="project-img">
            <div class="description" id="space">
              <div class="title-description">
                SpaceFlix
                <span class="material-icons open-in">
                  open_in_new
                </span>
              </div>
              SpaceFlix é um projeto de streaming pessoal, onde simula um web site de streaming com uma variedade de mais
              de 90 titulos famosos dentre filmes, séries e animes.
            </div>
          </div>
          <div v-on:mouseover="showDescription('weather')" v-on:mouseleave="hideDescription('weather')">
            <img src="@/assets/app-previsao-do-tempo.png" class="project-img">
            <div class="description" id="weather">
              <div class="title-description">
                Weather App
                <span class="material-icons open-in">
                  open_in_new
                </span>
              </div>
              É um projeto de um aplicativo de previsão do tempo que fornece informações meteorológicas em tempo real e
              previsões detalhadas para os usuários. Este aplicativo foi desenvolvido com o uso de API HG Weather.
            </div>
          </div>
          <div v-on:mouseover="showDescription('jokenpo')" v-on:mouseleave="hideDescription('jokenpo')">
            <img src="@/assets/jokenpo.png" class="project-img">
            <div class="description" id="jokenpo">
              <div class="title-description">
                Pedra, Papel e Tesoura
                <span class="material-icons open-in">
                  open_in_new
                </span>
              </div>
              Este projeto é um jogo interativo e divertido de "Pedra, Papel e Tesoura" criado com o framework Vue.js. Ele
              oferece uma experiência de jogo clássica, permitindo que os usuários escolham entre pedra, papel ou tesoura
              e competir contra o computador.
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="index-container">
      <div class="nav-index" v-on:click="index('0')">
        <div :style="selected('0')">
        </div>
      </div>
      <div class="nav-index" v-on:click="index('1')">
        <div :style="selected('1')">
        </div>
      </div>
      <div class="nav-index" v-on:click="index('2')">
        <div :style="selected('2')">
        </div>
      </div>
      <div class="nav-index" v-on:click="index('3')">
        <div :style="selected('3')">
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      teste: '0'
    }
  },
  methods: {
    showDescription(id) {
      let description = document.getElementById(id)
      description.style.bottom = '0'
    },
    hideDescription(id) {
      let description = document.getElementById(id)
      description.style.bottom = '-21.5vh'
    },
    index(section) {
      let showWindow = document.getElementById('container')
      showWindow.style.top = '-' + section + '00vh'
      this.teste = section

    },
    selected(index) {
      if (index == this.teste) return 'background-color: var(--red);'
    }
  }
}
</script>
<style>
:root {
  --red: rgb(216, 0, 0);
}

body {
  margin: 0;
  font-family: 'kanit';
}

.window {
  width: 100%;
  color: rgb(211, 206, 206);
  background-image: url("@/assets/wallpaper.svg");
  position: relative;
  height: 100vh;
  overflow: hidden;
}

.index-container {
  position: absolute;
  left: 3vw;
  top: 44vh;
  display: flex;
  flex-direction: column;
  gap: 1vh;
  opacity: 0;
  transition: ease-in-out;
  transition-delay: 3s;
}

.window:hover>.index-container {
  opacity: 1;
  transition: 200ms ease-in-out;
}

.nav-index {
  height: 3vh;
  width: 3vh;
  clip-path: polygon(25% 10%, 75% 10%, 95% 50%, 76% 90%, 25% 90%, 5% 50%);
  background-color: var(--red);
  display: flex;
  justify-content: center;
  align-items: center;
  transform: rotate(90deg);
}

.nav-index>div {
  clip-path: polygon(25% 10%, 75% 10%, 95% 50%, 76% 90%, 25% 90%, 5% 50%);
  height: 2.5vh;
  width: 2.5vh;
  background-color: #161616;
  cursor: pointer;
}

.nav-index>div:hover {
  background-color: var(--red)
}

.header {
  height: 8vh;
  width: 100vw;
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  padding: 0 2vw;
  align-items: center;
  font-size: 3vh;
  position: fixed;
  z-index: 2;
  background-color: #161616c4;
}

.header-name {
  font-size: 5vh;
  display: flex;
  gap: 1vh;
}

.nav-links {
  display: flex;
  gap: 3vw;
  cursor: pointer;
  width: 30vw;
  font-size: 3.5vh;
  margin-left: -5vw;
}

.nav-links>div:hover {
  color: var(--red);
}

button {
  width: 10vw;
  padding: 0.5vh 1vh;
  height: fit-content;
  font-size: 3vh;
  cursor: pointer;
  background-color: rgb(211, 206, 206);
  border: none;
  border-radius: 10px;
  font-family: 'kanit';
}

a {
  text-decoration: none;
  color: black;
}

button:hover {
  background-color: var(--red);
}

button:hover>a {
  color: rgb(211, 206, 206);
}

.row-container {
  height: 100vh;
  position: absolute;
  top: 0;
  transition: top 1s ease-in-out;
}

.about-me-container,
.skills,
.projects,
.presentation-container {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  display: flex;
  align-items: center;
}

.presentation {
  width: 50vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-size: 5vh;
  gap: 2vh;
  color: rgb(168, 168, 168);
}

.presentation-img {
  height: 60vh;
}

.greeting {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  width: 44vw;
  padding: 0 1vw;
  line-height: 5.5vh;
}

.greeting>div:not(:last-child) {
  margin-left: 1vh;
  font-style: italic;
  color: rgb(224, 224, 224);
}

.presentation-inks {
  display: flex;
  align-items: center;
  gap: 2vw;
  margin-left: 1vw;
}

.link {
  cursor: pointer;
  height: 6.5vh;
}

.about-me-container {
  gap: 3vw;
  flex-direction: column;
}

.about-me-container>div {
  display: flex;
  gap: 5vw;
  align-items: center;
}

.photo {
  width: 25vw;
  height: 25vw;
  border-radius: 50%;
}

.about-me {
  width: 50vw;
  font-size: 3vh;
}

.title-about {
  font-size: 7vh;
  margin-left: -5vw;
}

.projects,
.skills {
  flex-direction: column;
  font-size: 7vh;
  gap: 5vh;
}

.skill-icon {
  height: 15vh;
}

.skills>div {
  display: flex;
  align-items: center;
  gap: 2vw;
}

.skills>div>div {
  font-size: 5vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #161616c5;
  padding: 1vh;
  border-radius: 10px;
  cursor: pointer;
}

.skills>div>div:hover {
  background-color: #292929c5;
  color: var(--red);
}

.my-projects {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3vw;
  flex-wrap: wrap;
  margin-bottom: 2vh;
}

.my-projects>div {
  width: 32vw;
  height: 30vh;
  position: relative;
  overflow: hidden;
  border-radius: 10px;
}

.project-img {
  width: 100%;
  height: 35vh;
  border-radius: 10px;
  transition: ease-in-out 200ms;
  cursor: pointer;
}

.title-description {
  font-size: 2.5vh;
  color: white;
  margin-bottom: 1vh;
  font-style: italic;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.open-in {
  color: rgb(211, 206, 206);
  cursor: pointer;
  font-size: 2.5vh;
}
.open-in:hover {
  color: var(--red);
}
.description {
  font-size: 2.1vh;
  width: 100%;
  position: absolute;
  padding: 1vh;
  box-sizing: border-box;
  background-color: #000000f5;
  border-radius: 10px;
  transition: bottom 1s;
  bottom: -21.5vh;
  height: 21.5vh;
}
</style>