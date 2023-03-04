<template>
  <div class="welcome-section">
    <div class="main-img">
      <img src="../assets/main-img.jpg" alt="A picture of us" />
    </div>
    <div class="content">
      <div class="title-container">
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
    </div>
  </div>
</template>
<style lang="scss">
@import "../scss/mixins";
@import "../scss/variables";
.welcome-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  .main-img {
    img {
      width: 100%;
    }
  }
  .content {
    margin: 12px;
    .title-container {
      @include uppercase;
      @include container;
      display: flex;
      flex-direction: column;
      justify-content: center;
      text-align: center;
      width: 100%;
      .title {
        width: 100%;
        margin: auto;
        letter-spacing: $title-spacing;
        font-size: $text-lg;
      }
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
        .and {
          font-style: italic;
          font-size: $text-sm;
        }
      }
    }
  }
}
</style>
