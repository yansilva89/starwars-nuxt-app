<template>
  <div class="home">
    <DivPage>
      <template #left>
        <div class="content-left">
          <Logo class="animeLeft" width="18rem" />
        </div>
      </template>

      <template #right>
        <div class="content-right">
          <div class="text animeRight">
            <h1>seja bem vindo à star wars app</h1>
            <p>aqui você conhecerá todo o básico do universo star wars - personagens, planetas, aeronaves, filmes, etc. clique no botão de acesso e divirta-se!</p>
          </div>
          <Button class="animeRight" btn-text="visualizar listas" @click="() => handleClick()" />
        </div>
      </template>
    </DivPage>
  </div>
</template>

<script lang="ts">
import vue from 'vue'
export default vue.extend({
  methods: {
    handleClick () {
      this.$router.push('/list-links')
    }
  }
})
</script>

<style lang="scss" scoped>
.home {
  height: 100vh;
  background-image: url('~assets/images/space-bg-1.jpg');
  background-size: contain;
  display: flex;
  flex-direction: column;
  align-items: center;
  .content-left {
    height: 100%;
    display: flex;
    justify-content: center;
  }
  .content-right {
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #1c1c21;
    padding: 0 5rem;
    .text {
      width: 100%;
      color: #F2E73A;
      h1, p {
        margin-bottom: 2rem;
      }
      h1 {
        font-size: 3rem;
        line-height: 45px;
        text-align: center;
        letter-spacing: -5px;
      }
      p {
        font-size: 1.3rem;
        text-align: justify;
        color: #fff;
        letter-spacing: -2px;
      }
    }
  }
}
</style>
