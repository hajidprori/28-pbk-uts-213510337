<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="black">{{ msg }}</h1>
    <h3>
      Tentang Saya  <br>

      <a href="https://instagram.com/mhajidd?igshid=OTk0YzhjMDVlZA==/" target="_blank" rel="noopener"><img src="@/assets/IG.png" alt=""></a> +
      <a href="https://github.com/hajidprori/28-pbk-uts-213510337/" target="_blank" rel="noopener"><img src="@/assets/github.png" alt=""></a>.
    </h3>
  </div>
</template>

<style scoped>

img{
  width: 5%;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
  font-family:monospace;
  font-weight: bold

}

h3 {
  font-size: 1.2rem;
  font-family:monospace;
  font-weight: bold
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
