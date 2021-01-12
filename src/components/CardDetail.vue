<template>
  <div>
    <label>
      <input type="checkbox" />
      <div class="flip-card">
        <div class="front">
          <h1>{{ item.front }}</h1>
          <!-- <h2>Smart Web Developer</h2>
        <b>adpaul@gmail.com</b>
        <p>Click to flip</p> -->
        </div>
        <div class="back">
          <h1>{{ item.back.title }}</h1>
          <hr />
          <!-- <pre class="code">{{ item.back.code }}</pre> -->
          <pre class="code" v-for="code in item.back.code" :key="code.id">
            {{ code }}
          </pre>
          <!-- <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since forever.
        </p> -->
          <hr />
          <p class="click">Click to flip</p>
        </div>
      </div>
    </label>
  </div>
</template>

<script>
export default {
  name: "CardDetail",
  props: {
    item: Object,
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #4e699d;
  font-family: sans-serif;
}

label {
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 280px;
  height: 350px;
  perspective: 1000px;
  transform-style: preserve-3d;
  transform: translate(-50%, -50%);
  cursor: pointer;
}

.flip-card {
  position: relative;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: all 0.5s ease-in-out;
  z-index: 1;
}

.flip-card .front,
.flip-card .back {
  position: absolute;
  width: 100%;
  height: 100%;
  text-align: center;
  background: #fff;
  backface-visibility: hidden;
  border-radius: 0 20px 0 20px;
}

.flip-card .back {
  transform: rotateX(180deg);
  color: #000;
  background: #fff;
}

label:hover .flip-card {
  transform: rotateX(2deg);
  box-shadow: 0 20px 20px rgba(50, 60, 60, 0.2);
}

input {
  display: none;
}

:checked + .flip-card {
  transform: rotateX(180deg);
}
label:hover :checked + .flip-card {
  transform: rotateX(175deg);
  box-shadow: 0 20px 20px rgba(255, 255, 255, 0.2);
}

.front img {
  width: 110px;
  height: 110px;
  margin: 30px 0 20px 0;
  border-radius: 50%;
}

.front h1 {
  font-size: 18px;
  color: #499bef;
  margin: 0;
}
.front h2 {
  font-size: 12px;
  color: #4e699d;
  margin: 12px 0 12px 0;
}

.front b {
  font-size: 14px;
  color: #424752;
  margin: 0 0 35px 0;
  display: block;
}

.front p,
.back .click {
  font-size: 8px;
  font-weight: 600;
}

.back h1 {
  color: #424752;
  margin: 30px 0 0 0;
}

hr {
  width: 100px;
  margin: 15px auto 10px auto;
}

.back p {
  font-size: 12px;
  color: #000;
  padding: 0 18px;
  line-height: 30px;
  text-align: center;
  margin: 0 auto;
}
.code {
  font-size: 12px;
}
</style>
