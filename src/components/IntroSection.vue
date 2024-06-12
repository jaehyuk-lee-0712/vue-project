<template>
  <section id="intro">
    <div class="intro__inner">
      <h2 class="intro__title">port developer</h2>
      <div class="intro__lines" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
      <div class="intro__text">
        <div class="text">
          <div>talent is</div>
          <div>found at the end of the</div>
          <div>effort</div>
        </div>
        <div class="img">
          <img
            src="data:image/jpeg;base64,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"
            alt=""
          />
        </div>
      </div>
      <div class="intro__lines" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#intro {
  height: 100vh;

  .intro__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 16px;
    .intro__title {
      font-size: 10vw;
      line-height: 1;
      font-weight: 800;
      white-space: nowrap;
      text-transform: uppercase;
      letter-spacing: -0.3vw;
    }

    .intro__items {
      display: none;
    }

    .intro__text {
      width: 100%;
      height: 40vh;
      background-color: var(--black);
      color: var(--white);
      align-items: center;
      justify-content: center;
      flex-direction: column;
      position: relative;

      .text {
        font-size: 3vw;
        line-height: 1;
        font-weight: 900;
        text-transform: uppercase;
        text-decoration: underline;
        text-align: center;
        position: relative;
        z-index: 100;
        transition: all 0.3s;
        cursor: all-scroll;
      }
      .img {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        width: 30vh;
        height: 30vh;
        border-radius: 50%;
        overflow: hidden;
        filter: grayscale(100%);
        transition: all 0.3s;
      }
    }

    .intro__lines {
      width: 100%;
      .line {
        display: block;
        width: 100%;
        height: 1px;
        background-color: var(--black);
        margin-bottom: 0.5vw;

        &:nth-child(1) {
          height: 1px;
        }
        &:nth-child(2) {
          height: 3px;
        }
        &:nth-child(3) {
          height: 5px;
        }
        &:nth-child(4) {
          height: 7px;
        }
        &:nth-child(5) {
          height: 9px;
        }
        &:nth-child(6) {
          height: 11px;
        }
        &:nth-child(7) {
          height: 13px;
        }
      }
    }
  }
}
</style>
