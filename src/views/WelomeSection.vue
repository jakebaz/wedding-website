<template>
  <div class="welcome-section">
    <div class="main-img">
      <img src="../assets/main-img.jpg" alt="A picture of us" />
    </div>
    <h1 class="title">
      <span>Ellie</span>
      <div class="break">
        <div class="line line__left"></div>
        <span class="and">&</span>
        <div class="line line__right"></div>
      </div>
      <span>Jake</span>
    </h1>
  </div>
</template>
<style lang="scss">
@import "../scss/mixins";
@import "../scss/variables";
.welcome-section {
  .main-img {
    img {
      width: 100%;
    }
  }
  .title {
    @include uppercase;
    @include container;
    display: flex;
    flex-direction: column;
    text-align: center;
    .break {
      position: relative;
      margin: 25px auto;
      width: 100%;
      .line {
        content: "";
        display: block;
        width: 40%;
        height: 3px;
        position: absolute;
        top: 50%;
        background: $text-primary;
        &__left {
          left: 0;
        }
        &__right {
          right: 0;
        }
      }
    }
  }
}
</style>
