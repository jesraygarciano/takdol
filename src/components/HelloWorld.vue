<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <div @mousemove="monstah" class="ufo">
      <div class="monster">
        <div class="body">
          <div class="ear"></div>
          <div class="ear"></div>
          <div class="vampi-mouth">
            <div class="vampi-tooth">
            </div>
          </div>
        </div>
        <div class="eye-lid">
          <div class="eyes">
            <div class="eye"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
  // let ufo = document.querySelector('.ufo'),
  // ufo.addEventListener('mousemove', (e) => {

  // });

  name: 'HelloWorld',
  data: {
    ufo : document.querySelector('.ufo')
  },
  methods: {
    monstah : (e) => {
      let eye = document.querySelector('.eyes');
      let mouseX = (eye.getBoundingClientRect().left);
      let mouseY = (eye.getBoundingClientRect().top);
      let radianDegrees = Math.atan2(e.pageX - mouseX, e.pageY - mouseY);
      let rotationDegrees = (radianDegrees * (180/Math.PI) * -1) + 180;
      eyes.style.transform = `rotate(${rotationDegrees}deg`
    }
  },

  props: {
    msg: String
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.monster{
  color: #7cb342;
}
.eye-lid{
  text-align: center;
  display: flex;
  font-size: 0.65em;
  width: 1em;
  height: 1em;
  position: absolute;
  left: 0.25em;
  top: 0.3em;
  background-color: white;
  border-radius: 0.5em 0.5en 0.5em 0.5em / 0.6em 0.6em 0.4em 0.4em;
  box-shadow: 0.03em 0.14em rgba(0,0,0,0.1);

  animation-name: blink;
  animation-timing-function: ease-in-out;
  animation-direction: forwards;
  animation-iteration-count: infinite;
  animation-duration: 10s;

  // animation: blink forwards infinite 10s ease-in-out;
}
.eyes {
  text-align: center;
  display: flex;
  font-size: 0.65em;
  width: 1em;
  height: 1em;
  position: absolute;
  left: 0.25em;
  top: 0.3em;
}

.eye{
  position: relative;
  display: inline-block;
  border-radius: 50%;
  width: 75%;
  height: 75%;
  background-color: black;
  border-radius: 50%;
}

.eye::after{ /*white shadow*/
  --pupil-size : 0.2em;
  position: absolute;
  top: 0.05em;
  left: 0.3em;
  width: var(--pupil-size);
  height: var(--pupil-size);
  background: white;
  border-radius: 50%;
  content: " ";
}

// h3 {
//   margin: 40px 0 0;
// }
// ul {
//   list-style-type: none;
//   padding: 0;
// }
// li {
//   display: inline-block;
//   margin: 0 10px;
// }
// a {
//   color: #42b983;
// }
</style>
