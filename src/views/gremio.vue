<template>
  <div>
    <button type="button" class="btn btn-light-outline d-flex" @click="mute">
      <i class="fa-solid fa-volume-high text-white" v-if="!this.is_muted"></i
      ><i class="fa-solid fa-volume-xmark text-white" v-else></i>
    </button>
    <h1 class="text-white">Gremio</h1>
    <div class="m-4">
      <i class="fa-solid fa-star fa-2xl estrela1 floaters"></i>
      <i class="fa-solid fa-star fa-2xl estrela2 floaters"></i>
      <i class="fa-solid fa-star fa-2xl estrela3 floaters"></i>

      <img class="floaters logo" src="../assets/gremio.png" />
    </div>
  </div>
  <div>
    <img class="small m-2 floaters" src="../assets/rs.jpg" />
    <span class="text-white">O Maior tricolor do Rio Grande do Sul</span>
    <span><img class="small m-2 floaters" src="../assets/rs.jpg" /></span>
  </div>
  <div class="agrup-content">
    <div class="caixa">
      <div>
        <img src="../assets/gremio.png" />
        <h2 class="m-2"><b>título</b></h2>
        <p class="text-black font-10">
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s, when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
        </p>
      </div>
    </div>
    <div class="caixa">caixa</div>
  </div>
  <audio controls autoplay id="audio">
    <source src="../assets/audio/hino-gremio-rs.mp3" type="audio/mpeg" />
    Your browser does not support the audio element.
  </audio>
</template>

<script>
// @ is an alias to /src

export default {
  name: "gremio-view",
  data() {
    return {
      is_muted: false,
    };
  },
  methods: {
    mute() {
      this.is_muted = !this.is_muted;
      const x = document.getElementById("audio");
      x.muted = this.is_muted;
    },
  },
};
</script>

<style>
body {
  background: linear-gradient(to bottom, black, #0066a8, #0066a8, #f2f2f2);
  position: relative;
}

h1 {
  font-size: 100px;
}
span {
  font-size: 25px;
}
.logo {
  box-sizing: border-box;
  overflow: hidden;
  border-radius: 50%;
}

.small {
  display: relative;
  height: 30px;
}
.floaters {
  transform: translatey(0px);
  animation: float 2s ease-in-out infinite;
}

@keyframes float {
  0% {
    box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
    transform: translatey(0px);
  }
  50% {
    box-shadow: 0 25px 15px 0px rgba(0, 0, 0, 0.2);
    transform: translatey(-5px);
  }
  100% {
    box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
    transform: translatey(0px);
  }
}
.estrela1 {
  color: yellow;
  position: absolute;
  margin-top: 25px;
}
.estrela2 {
  color: yellow;
  position: absolute;
  margin-left: 93px;
}
.estrela3 {
  color: yellow;
  position: absolute;
  margin-top: 25px;
  margin-left: 186px;
}
audio {
  display: none;
}
.agrup-content {
  border-radius: 10px;
  width: 1000px;
  height: 2000px;
  display: flex;
  background-image: linear-gradient(
      to bottom,
      rgb(0, 0, 0),
      rgba(0, 0, 0, 0.956),
      rgba(0, 0, 0, 0.708)
    ),
    url("../assets/Arena-Grêmio-.jpg");
  background-size: 1300px 1000px;
  background-position: center;
  background-attachment: fixed;
  margin: auto;
  margin-top: 200px;
}
.caixa {
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.875);
  width: 400px;
  height: 400px;
  margin: 50px;
}
.caixa div img {
  height: 200px;
  height: 200px;
  filter: drop-shadow(0px 20px 5px #000003);
}

p {
  font-size: 14px;
  margin: auto;
}
</style>
