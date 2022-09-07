<template>
  <div>
    <div class="section-1">
      <div class="bg-image">
        <img class="background" src="/images/section-1-bg.jpg" alt="" />
        <img src="/images/section-1-grid-bg.svg" alt="" />
      </div>
      <div class="inner">
        <div class="copy">
          <h1>POWERED<br />by PEOPLE</h1>
          <p>Connect. Conserve. Earn. Sustain.</p>
          <div class="ctas">
            <a href="#" class="button">Add me to the waitlist</a>
            <a href="#" class="link">Join the discord</a>
          </div>
        </div>
        <div class="image">
          <img src="/images/section-1-image.png" alt="" />
        </div>
      </div>
      <div class="inner2">
        <h2>Changing the World With</h2>
        <ul class="large">
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-lerer-hippeau.png" alt="" />
              <img
                class="hover"
                src="/images/logo-lerer-hippeau-hover.png"
                alt=""
              />
            </a>
          </li>
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-lattice.png" alt="" />
              <img class="hover" src="/images/logo-lattice-hover.png" alt="" />
            </a>
          </li>
        </ul>
        <ul class="small">
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-dcg.png" alt="" />
              <img class="hover" src="/images/logo-dcg-hover.png" alt="" />
            </a>
          </li>
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-coinshares.png" alt="" />
              <img
                class="hover"
                src="/images/logo-coinshares-hover.png"
                alt=""
              />
            </a>
          </li>
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-vaynerfund.png" alt="" />
              <img
                class="hover"
                src="/images/logo-vaynerfund-hover.png"
                alt=""
              />
            </a>
          </li>
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-allegory.png" alt="" />
              <img class="hover" src="/images/logo-allegory-hover.png" alt="" />
            </a>
          </li>
          <li>
            <a href="#" target="_blank">
              <img src="/images/logo-gaingels.png" alt="" />
              <img class="hover" src="/images/logo-gaingels-hover.png" alt="" />
            </a>
          </li>
        </ul>
      </div>
    </div>
    <div class="section-2">
      <div class="bg-image">
        <img src="/images/section-2-grid-bg.svg" alt="" />
      </div>
      <div class="inner">
        <div class="image">
          <img src="/images/section-2-image.jpg" alt="" />
        </div>
        <div class="copy">
          <h3>Small Actions.<br /><span>Massive Impact.</span></h3>
          <p>
            Collective actions yield outsized results. With the React Network,
            you earn for connecting your smart thermostat, home battery, or
            other smart devices. React makes small, infrequent adjustments to
            stabilize the power grid, supercharging more renewable deployments
            and reducing our reliance on dirty power plants.
          </p>
        </div>
      </div>
    </div>
    <div class="section-3">
      <div class="bg-image">
        <img class="background" src="/images/section-3-bg.jpg" alt="" />
        <img src="/images/section-3-grid-bg.svg" alt="" />
      </div>
      <div class="inner">
        <h2>Future Focused</h2>
        <ul>
          <li>
            <img src="/images/icon-people.svg" alt="" />
            <h3>Community Ownership</h3>
            <p>Platforms should be owned by those who build them.</p>
          </li>
          <li>
            <img src="/images/icon-snowflake.svg" alt="" />
            <h3>Environmental Sustainability</h3>
            <p>
              A sustainable energy system is better for the planet and for
              people.
            </p>
          </li>
          <li>
            <img src="/images/icon-trophy.svg" alt="" />
            <h3>Eyes On The Prize</h3>
            <p>Sustainable actions should be rewarded, not taxed.</p>
          </li>
        </ul>
      </div>
      <div class="inner2">
        <div class="copy">
          <h3>
            <span>Fixing the Planet</span><br />
            is Good Business.
          </h3>
          <p>
            Earning is as easy as connecting your smart thermostat or home
            battery system. Your devices immediately start minting React tokens
            for participating. Passive income, for an active fight against
            climate change and unstable energy grids
          </p>
          <p>
            Why crypto? Crypto enables React to be owned and operated by its
            community, meaning value is returned to you and not middlemen. Your
            smart devices, your network.
          </p>
          <ul>
            <li>
              React’s digital currency is clean. Minting React tokens
              accelerates our sustainable energy future.
            </li>
          </ul>
        </div>
        <div class="image">
          <img src="/images/section-3-image.jpg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Home",
    };
  },
};
</script>

<style lang="scss" scoped>
.section-1 {
  position: relative;
  padding-top: 19.8vw;
  padding-bottom: 12.7vw;
  @include gutter(padding-left);
  @include gutter(padding-right);
  overflow: hidden;

  .bg-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;

    img {
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: auto;
    }

    img.background {
      object-fit: cover;
      height: 100%;
    }
  }

  .inner {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;

    .copy {
      h1 {
        color: $yellow;
        @include clamp("font-size", 45px, 3.2vw, 60px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: uppercase;
        margin-bottom: 1em;
      }

      p {
        margin-bottom: 2em;
      }

      .ctas {
        display: flex;
        align-items: center;
      }
    }

    .image {
      width: 55%;
      flex-shrink: 0;

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }
  }

  .inner2 {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;
    padding-top: 31vw;

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      text-align: center;
      letter-spacing: 0.04em;
      color: $dark_green;
      margin-bottom: 2.5em;
    }

    ul {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      width: 100%;

      &.large {
        li {
          width: 21.4vw;
        }
      }

      &.small {
        justify-content: space-between;

        li {
          width: 13vw;

          a {
            img {
              width: 90%;
            }
          }
        }
      }

      li {
        flex-shrink: 0;
        margin-bottom: 5vw;

        a {
          position: relative;
          display: flex;
          justify-content: center;

          &:hover {
            img {
              opacity: 0;
            }

            img.hover {
              opacity: 1;
            }
          }

          img {
            display: block;
            width: 100%;
            height: auto;

            &.hover {
              position: absolute;
              top: 0;
              left: 50%;
              transform: translateX(-50%);
              opacity: 0;
              transition: 0.15s opacity;
            }
          }
        }
      }
    }
  }
}

.section-2 {
  position: relative;
  z-index: 1;
  background-color: $dark_green;

  display: flex;
  align-items: center;

  .bg-image {
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    img {
      display: block;
      width: 100%;
      height: auto;
    }
  }

  .inner {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: space-between;
    @include gutter(padding-left);
    @include gutter(padding-right);
    margin-top: -10vw;

    .image {
      width: 48%;
      flex-shrink: 0;
      padding: 2.55vw;

      img {
        display: block;
        width: 100%;
        height: auto;
      }
    }

    .copy {
      width: 48%;
      flex-shrink: 0;
      padding: 0 2.2vw;

      h3 {
        font-weight: 400;
        @include clamp("font-size", 34px, 3.13vw, 60px);
        line-height: 120%;
        letter-spacing: 0.04em;
        text-transform: capitalize;
        margin-bottom: 1em;

        span {
          color: $yellow;
        }
      }
    }
  }
}

.section-3 {
  position: relative;
  padding-top: 11.5vw;
  padding-bottom: 12.7vw;
  @include gutter(padding-left);
  @include gutter(padding-right);
  overflow: hidden;

  .bg-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;

    img {
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: auto;
    }

    img.background {
      object-fit: cover;
      height: 100%;
    }
  }

  .inner {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;

    h2 {
      font-weight: 400;
      @include clamp("font-size", 34px, 4.17vw, 80px);
      line-height: 120%;
      text-align: center;
      letter-spacing: 0.04em;
      color: $dark_green;
      margin-bottom: 2em;
    }

    ul {
      display: flex;
      justify-content: space-between;

      li {
        width: calc(33.3333% - 1.5vw);
        background-color: $dark_green;
        border-radius: 20px;
        box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.25);
        padding: 4vw 2vw;

        img {
          display: block;
          @include clamp("width", 56px, 3.65vw, 70px);
          height: auto;
          margin-bottom: 2vw;
        }

        h3 {
          font-weight: 400;
          @include clamp("font-size", 32px, 2.35vw, 45px);
          line-height: 120%;
          padding-bottom: 0.5em;
          margin-bottom: 0.75em;
          border-bottom: 3px solid $yellow;
        }
      }
    }
  }

  .inner2 {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 3vw;
    padding-right: 4.5vw;
    padding-top: 31vw;
  }
}
</style>
