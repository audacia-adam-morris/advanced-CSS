<script setup>
const toggles = ref({});

onMounted(() => {
  console.log('dfsdf');
});
</script>

<template>
  <div class="app">
    <!-- <NuxtWelcome /> -->
    <h1>Advanced CSS</h1>
    <section>
      <div class="title">Unit values</div>
      <p><code>Absolute length units</code></p>
      <p>
        <code
          >cm Centimeter, mm Millimeters, Q Quarter-millimeters, in Inches, pt
          Points, px Pixels
        </code>
      </p>
      <p><code>Relative length units</code></p>
      <p>
        <code
          >em Font size of the parent,<br />rem Font size of root element -
          (User can custom set the browser default font-size),<br />vw 1% of
          viewport width,<br />vh 1% of viewport height,<br />vmin 1% of the
          viewport's smaller dimention,<br />vmax 1% of the viewport's larger
          dimention<br />
        </code>
      </p>

      <div class="value value--vmin-20">Hero Text</div>
    </section>

    <section>
      <div class="title">Transition</div>
      <p>
        <code>transition: name | duration | easing function | delay</code>
      </p>
      <p>
        <code>transition: font-size | 1s | ease-in-out | 20ms</code>
      </p>
      <div
        class="value value--transition"
        :class="{ 'value--transition--on': toggles.transition }"
        @click="toggles.transition = !toggles.transition"
      >
        Hello World
      </div>
    </section>

    <section>
      <div class="title">Transform</div>
      <p>
        <code
          >transform: translate | translate3d | rotate | rotateY | rotateX |
          rotateZ</code
        >
      </p>
      <p>
        <code>transform: rotate(180deg)</code>
      </p>
      <div
        class="value value--transition-transform"
        :class="{ 'value--transition-transform--on': toggles.animation }"
        @click="toggles.animation = !toggles.animation"
      >
        Hello World
      </div>
    </section>

    <section>
      <div class="title">Drop Shadow</div>
      <div class="value value__box-shadow--1">This box has shadows 1</div>
      <div class="value value__box-shadow--2">This box has shadows 2</div>
      <div class="value value__box-shadow--3">This box has shadows 3</div>
    </section>

    <section>
      <div class="title">Colours</div>
      <p>
        <code>hex, rgb, rgba, hsl, hsla</code>
      </p>
      <div class="value">
        <p class="hex">Hello World</p>
        <p class="rgb">Hello World</p>
        <p class="rgba">Hello World</p>
        <p class="hsl">Hello World</p>
        <p class="hsla">Hello World</p>
      </div>
    </section>

    <section>
      <div class="title">Filter</div>
      <pre><code>filter: blur(5px);
filter: brightness(0.4);
filter: contrast(200%);
filter: drop-shadow(16px 16px 20px blue);
filter: grayscale(50%);
filter: hue-rotate(90deg);
filter: invert(75%);
filter: opacity(25%);
filter: saturate(30%);
filter: sepia(60%);</code></pre>
      <div class="value">
        <img
          :class="{ 'filter-on': toggles.filter }"
          @click="toggles.filter = !toggles.filter"
          src="https://source.unsplash.com/random?dog"
          alt=""
        />
      </div>
    </section>

    <section>
      <div class="title">Object Fit</div>
      <div class="value">
        <div class="object-fit-box">
          <img
            :class="{ 'object-fit-box--on': toggles.objectFit }"
            @click="toggles.objectFit = !toggles.objectFit"
            src="https://source.unsplash.com/random?dog"
            alt=""
          />
        </div>
      </div>
    </section>

    <section>
      <div class="title">:has() - (enable flag in chrome)</div>
      <div class="value">
        <br />
        <a href="https://codepen.io/t_afif/full/BaxzraM" target="_blank"
          >https://codepen.io/t_afif/full/BaxzraM</a
        ><br /><br />
        <a
          href="https://www.youtube.com/watch?v=OGJvhpoE8b4&feature=youtu.be"
          target="_blank"
        >
          https://www.youtube.com/watch?v=OGJvhpoE8b4&feature=youtu.be
        </a>
      </div>
    </section>

    <section>
      <div class="title">Perspective</div>
      <div class="value">
        <a
          href="https://css-tricks.com/how-css-perspective-works/"
          target="_blank"
          >https://css-tricks.com/how-css-perspective-works/</a
        >
      </div>
    </section>
  </div>
</template>

<style lang="scss">
*,
*:before,
*:after {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: 'Inter', sans-serif;
  background: linear-gradient(36deg, darken(#fff, 2%), darken(#fff, 8%));
}

.app {
  padding: 40px;

  h1 {
    font-size: 2rem;
    margin: 0 0 40px;
  }

  section {
    margin-bottom: 20px;
    padding: 20px;
    border-radius: 12px;
    background: #fff;
    box-shadow: 0 0 40px -10px rgba(#111, 0.08);

    .value {
      font-weight: 800;

      &--vmin-20 {
        font-size: 10vmin;
        text-align: center;
      }

      &--transition {
        font-size: 2rem;
        padding: 20px;
        transition: font-size 1s ease-in-out 1s;

        &--on {
          font-size: 1rem;
        }
      }

      &--transition-transform {
        position: relative;
        font-size: 2rem;
        padding: 20px;
        transition: 1s;
        background: #111;
        transition: 1s ease-in-out;
        color: #fff;

        &--on {
          transform: rotate(180deg);
          transform: translate3d(0, 0, 100px) rotate(45deg);
          transform-origin: bottom;
          background: red;
        }
      }

      // @media (prefers-reduced-motion) {
      //   transition: none!important;
      // }

      &__box-shadow {
        &--1 {
          margin: 40px 0;
          padding: 20px;
          box-shadow: 0 0 10px 10px rgba(0, 0, 0, 0.2);
        }

        &--2 {
          margin: 40px 0;
          padding: 20px;
          border-radius: 8px;
          box-shadow: 0 1px 10px gray;
        }

        &--3 {
          margin: 40px 0;
          padding: 20px;
          border-radius: 8px;
          box-shadow: 0 4px 20px -4px rgba(0, 0, 0, 0.2);
        }
      }

      .hex {
        color: #666;
      }
      .rgb {
        color: rgb(100, 100, 255);
        // red, green, blue
      }
      .rgba {
        color: rgba(255, 0, 255, 1);
        // red, green, blue, alpha
      }
      .hsl {
        margin: -1px 0 0;
        color: hsl(900, 100%, 50%);
        // hue, saturation, lightness
        border: 1px solid darken(#fff, 8%);
        padding: 10px;
      }

      .hsla {
        color: hsla(300, 100%, 50%, 1);
        // hue, saturation, lightness, alpha
      }

      img {
        width: 100%;

        &.filter-on {
          filter: hue-rotate(400deg);
        }
      }

      .object-fit-box {
        margin: 40px auto;
        width: 40vmin;
        height: 40vmin;
        background: #111;
        overflow: hidden;

        img.object-fit-box--on {
          width: 100%;
          height: 100%;
          object-fit: cover;
          // background: url() 50% 50% / cover no-repeat
          // background-size: contains;
          // why not use background-image?
          // Google SEO friendly
          // Google can scrape img tags/elements easier than background images
        }
      }
    }
  }
}
</style>
