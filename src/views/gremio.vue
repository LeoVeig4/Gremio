<template>
  <div>
    <button type="button" class="btn btn-light-outline d-flex" @click="mute">
      <i class="fa-solid fa-volume-high text-white" v-if="!this.is_muted"></i
      ><i class="fa-solid fa-volume-xmark text-white" v-else></i>
    </button>
    <h1 class="text-white">Grêmio</h1>
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
        <img class="caixa-img" src="../assets/camisa_marrom.jpg" />
        <h2 class="m-2"><b>Camisa Original</b></h2>
        <p class="text-black font-10">
          Originalmente, o uniforme do clube deveria ser havana (uma espécie de
          marrom), branco e preto. Mas como a cor era difícil de encontrar, a
          diretoria mudou para o azul.
        </p>
      </div>
    </div>
    <div class="caixa">
      <img class="caixa-img" src="../assets/getulio.jpg" />
      <h2 class="m-2"><b>Getúlio e o Grêmio</b></h2>
      <p class="text-black font-10">
        O Grêmio levou o Campeonato Gaúcho de 1930 antes do torneio terminar.
        Com a revolução que levou Getúlio Vargas à presidência do país, a
        disputa foi interrompida e o time consagrado campeão por ter a melhor
        campanha.
      </p>
    </div>
    <div class="caixa">
      <img class="caixa-img" src="../assets/bonde.jpg" />
      <h2 class="m-2"><b>O hino</b></h2>
      <p class="text-black font-10">
        Lupicínio compôs o verso “Até a pé nós iremos” inspirado em uma greve
        dos condutores de bonde em Porto Alegre. Sem transporte público, os
        torcedores do Grêmio tiveram que ir a pé para o Estádio dos Eucaliptos
        acompanhar um clássico contra o Internacional.
      </p>
    </div>
    <div class="caixa">
      <img class="caixa-img" src="../assets/lancheria.webp" />
      <h2 class="m-2"><b>Coca Cola Azul</b></h2>
      <p class="text-black font-10">
        Muitos anos mais tarde a Coca-Cola chegou a lançar uma latinha azul para
        ser comercializada em Porto Alegre. A questão da cor é séria mesmo: na
        Hamburgueria 1903, lanchonete oficial do Grêmio, o catchup recebe um
        aviso: “Infelizmente ainda não conseguimos mudar a cor”.
      </p>
    </div>
    <div class="caixa">
      <img class="caixa-img" src="../assets/grenal.png" />
      <h2 class="m-2"><b>Grenal</b></h2>
      <p class="text-black font-10">
        Um dos maiores clássicos do mundo é Grêmio x Internacional, apelidado
        por Gre-Nal. A disputa centenária ocorreu pela primeira vez no dia 18 de
        julho de 1909 e o Grêmio venceu a partida por 10 a 0.
      </p>
    </div>
    <div class="caixa">
      <img class="caixa-img" src="../assets/avalanche.gif" />
      <h2 class="m-2"><b>Avalanche</b></h2>
      <p class="text-black font-10">
        No antigo Estádio Olímpico, a torcida gremista tinha o ritual de
        comemorar os gols do clube com uma avalanche nas arquibancadas.
      </p>
    </div>
  </div>
  <div>
    <button class="bot-grande">Esteja por dentro dos Próximos jogos</button>
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
  min-height: 100vh;
  display: flex;
  flex-wrap: wrap;

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
  margin-top: 3rem;
  margin-bottom: 3rem;
}

.caixa {
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.875);
  width: 400px;
  height: 430px;
  margin: 50px;
}

.caixa-img {
  border-radius: 10%;
  height: 200px;
  height: 200px;
  filter: drop-shadow(0px 20px 5px #000003);
  margin-bottom: 1.25rem;
  margin-top: 1.25rem;
}

p {
  font-size: 14px;
  margin: 15px;
}

.bot-grande {
  width: 850px;
  margin: auto;
}
</style>
