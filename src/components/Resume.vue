<template>
  <div class="front-page">
    <h1>{{ msg }}</h1>
    <h3>Computer Engineering Senior at the University of Michigan</h3>

    <p class="description">Hi, Welcome to my page! I am passionate about backend 
      software engineering and embedded systems, and am seeking a full time position beginning in summer 2022. 
      This past summer I worked as a SDE intern for the Hotpads Rentals org within Zillow Group. 
      I gained experience with Java, SQL, and general industry coding standards.
      I studied abroad in France during the spring 2020 term pursuing my international minor, 
      and learned Vue.js and HTML/CSS when creating this site over summer 2020. 
      I have worked for the University of Michigan EECS Department as an instructional 
      aide for operating systems and programming and data structures courses. 
      In my free time I enjoy landscape photography, painting 
      landscapes with acrylics, and throwing on the pottery wheel.</p>
    
    <p class="punchline">Please feel free to take a look at my <a href="./rachel-connolly-resume-f21.pdf" target="_blank">Resume</a>.</p>


    <div class="links">

      <a href="https://github.com/rachcon" target="_blank" rel="noopener" >
        <img v-bind:class="bounce" class="icon" @mouseover="hoverOver()" @mouseout="hoverOut()" alt= "Github: @rachcon" src= "../assets/GitHub-Logo.png">
      </a>

      <a href="https://www.linkedin.com/in/rachcon/" target="_blank" rel="noopener">
        <img v-bind:class="bounce" class="icon" @mouseover="hoverOver()" @mouseout="hoverOut()" alt= "Linkedin" src= "../assets/linkedin-black.png">
      </a>

      <a v-bind:href="`mailto:` + 'rachcon@umich.edu'" target="_blank" rel="noopener">
        <img v-bind:class="bounce" class="icon" @mouseover="hoverOver()" @mouseout="hoverOut()" alt= "Email: rachcon@umich.edu" src= "../assets/emaili-icon.png">
      </a>

      <a href="https://www.instagram.com/noflashtravel" target="_blank" rel="noopener">
        <img v-bind:class="bounce" class="icon" @mouseover="hoverOver()" @mouseout="hoverOut()" alt= "Instagram: @noflashtravel" src= "../assets/glyph-logo.png">
      </a>

    </div>

    <footer>
        <p class="left-align">&copy; Rachel Connolly 2020, created with <a href="https://vuejs.org">Vue.js</a>.</p>
    </footer>

  </div>
</template>

<script>

export default {
  name: 'Resume',
  props: {
    msg: String
  },
  data() {
    return {
      bounce: []
    }
  },
  methods: {
    hoverOver() {
      console.log('over');
      this.bounce = ['animate__animated', 'animate__bounce']
    },
    hoverOut() {
      console.log('out');
      this.bounce = []
    }
  },
}
</script>


<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
h1 {
  font-size: 210%;
  color: black;
}
h3 {
  font-size: 125%;
  margin: 10px 0 2px 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: var(--accent-color);
  font-weight: bold;
}
.description {
  padding-right: 15%;
  padding-left: 15%;
}

.punchline {
  font-weight: bold;
  font-size: 1.1rem;
}
.icon {
  width: 40px;
  padding: 10px;
  margin: 10px 20px 50px 0;
}

.icon:hover{
  width: 45px;
  margin: 0 15px 50px 0;
}

.links {
  align-content: center;
  display: inline;
  flex-wrap: flex;
  padding: 1%;
}

footer {
  bottom: 1%;
  position: absolute;
  text-align: left;
  height: 2.5rem;
  padding: 1%;
  display: block;
  color: var(--accent-color);
  font-size: 12px;
}

front-page {

  margin: 0 auto;

  position: absolute;

  margin-left:auto;
  margin-right:auto;
  animation-name: fade;
  animation-duration: 0.7s;
  animation-timing-function: ease-out;
  animation-delay: 0;
  animation-direction: alternate;
  animation-fill-mode: forwards;
  animation-play-state: running;
}



.fade-enter-active {
  transition: opacity 0.5s;
}

@keyframes fade {
  0% {
    opacity: 0%;
  }
  50% {
    opacity: 50%;
  }
  100% {
    opacity: 100%
  }
}
</style>
