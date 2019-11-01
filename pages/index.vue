<template>
  <div class="container">
    <nav>
      <a class="nav-brand" href="#">
        <div>
          <i class="nes-icon trophy"></i>
          JFA
        </div>
      </a>
      <div class="filler"></div>
      <ul>
        <li class="nav-menu-item">
          <a href="#"><i class="nes-icon coin"></i>&nbsp;Blog</a>
        </li>
        <li class="nav-menu-item">
          <a href="#"><i class="nes-icon coin"></i>&nbsp;Resume</a>
        </li>
        <li class="nav-menu-item">
          <a href="#"><i class="nes-icon coin"></i>&nbsp;Contact</a>
        </li>
      </ul>
    </nav>
    <div class="main">
      <h1 id="kamusta">Kamusta!</h1>
      <div class="ako-po-container">
        <h2 id="ako-po">
          Ako po ay isang <br/>
          <transition name="slide-fade">
            <span class="highlight nes-text is-primary" v-if="ano === 1"
              >Batang&nbsp;90s</span
            >
          </transition>
          <transition name="slide-fade">
            <span class="highlight nes-text is-success" v-if="ano === 2"
              >Software&nbsp;Developer</span
            >
          </transition>
          <transition name="slide-fade">
            <span class="highlight nes-text is-error" v-if="ano === 3"
              >Tatay</span
            >
          </transition>
          <transition name="slide-fade">
            <span class="highlight nes-text is-success" v-if="ano === 4"
              >Fullstack&nbsp;Developer</span
            >
          </transition>
          <transition name="slide-fade">
            <span class="highlight nes-text is-success" v-if="ano === 5"
              >Waray</span
            >
          </transition>
          <transition name="slide-fade">
            <span class="highlight nes-text is-success" v-if="ano === 6"
              >Backend&nbsp;Developer</span
            >
          </transition>
        </h2>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
  components: {},

  data() {
    return {
      ano: 1
    };
  },

  methods: {
    hover: function() {}
  },

  mounted: function() {
    const self = this;
    setInterval(() => {
      this.ano += 1;
      if (this.ano > 6) {
        this.ano = 1;
      }
    }, 2100);

    // const peeps = [];

    // let peep = document.createElement("i");
    // peep.classList.add("nes-mario");
    // peep.style.left = 0;
    // peep.style.top = 0;
    // peep.style.position = "absolute";
    // // peep.style.left = `${Math.floor(Math.random() * 100)}vw`; // starting point on x-axis
    // // peep.style.top = `${Math.floor(Math.random() * 100)}vh`; // starting point on y-axis
    // //peep.style.transform = `scale(${Math.random()})`;
    // //peep.style.width = `${Math.random()}em`; // width of peep

    // let to = {
    //   x: Math.random() * 11, // distance to move along x-axis
    //   y: Math.random() * 12 // distance to move along y-axis
    // };

    // peep.animate(
    //   [
    //     { transform: "translate(0, 0)" }, // starting position is from css values
    //     { transform: `translate(calc(100vw - 90px), calc(100vh - 90px))` } // use randomly calculated values to set distance of movement
    //   ],
    //   {
    //     duration: (Math.random() + 1) * 2000, // random duration
    //     direction: "alternate", // go back and forth
    //     fill: "both",
    //     iterations: Infinity, // animation occurs forever
    //     easing: "ease-in-out" // slow movement
    //   }
    // );

    // this.$el.append(peep);

    //alert(this.$el);
  }
};
</script>

<style>
nav {
  display: flex;
  font-size: 1.4rem;
  align-items: center;
  height: 70px;
}

.nav-brand {
  display: flex;
  align-items: center;
  padding: 0 15px;
}

nav ul {
  list-style: none;
  padding: 0;
  display: flex;
  margin: 0;
  height: 100%;
}

.nav-menu-item {
  display: flex;
  padding: 0 15px;
  margin: 0 10px;
  height: 100%;
  align-items: center;
}

.nav-menu-item:hover,
.nav-brand:hover {
  background-color: rgb(187, 187, 187);
}

a:hover {
  text-decoration: none;
}

.nav-menu-item:hover .nes-icon.coin {
  animation: spinx 0.7s;
}

@keyframes spinx {
  0% {
    left: 0px;
  }
  25% {
    transform: scale(2) rotateY(90deg);
    left: 16px;
  }
  50% {
  }
  100% {
    left: 0px;
  }
}

.filler {
  flex-grow: 1;
}

/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all 0.9s ease;
}

.slide-fade-enter
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0.4;
}

.container {
  padding: 5px;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.highlight {
  background-color: rgb(214, 214, 214);
  padding: 15px;
  word-break: keep-all;
  word-wrap: normal;
}

.nes-icon {
  margin-right: 5px !important;
}

@media screen and (max-width: 800px) {
  body {
    background-color: rgba(255, 0, 0, 0.109);
  }
}

@media screen and (min-width: 801px) {
  body {
    background-color: rgba(0, 128, 0, 0.123);
  }

  .main {
    justify-content: center;
    align-items: center;
    text-align: center;
    margin: auto 0;
    width: calc(100vw-5px);
  }

  h1#kamusta {
    font-size: 2.9rem;
  }

  h2#ako-po {
    font-size: 2.7rem;
    height: 150px;
  }

  .ako-po-container {
      width: 70%;
      margin: 0 auto;
      margin-top:50px;
  }
}

</style>
