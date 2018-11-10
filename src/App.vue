<template>
  <div class="App o-container o-container--s o-vertical-spacing o-vertical-spacing--xl">
    <h1>Building a Simple Content Slider with Vue.js</h1>

    <section class="App__example o-vertical-spacing o-vertical-spacing--l">
      <h2>Basic Slider</h2>

      <SliderFrame>
        <div slot-scope="{ next, prev }">
          <SliderSlides>
            <SliderSlide class="o-vertical-spacing">
              <h3>Lorem Ipsum dolor</h3>
              <p>
                Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                diam nonumy eirmod tempor invidunt ut labore et dolore magna
                aliquyam erat, sed diam voluptua. At vero eos et accusam et
                justo duo dolores et ea rebum. Stet clita kasd gubergren.
              </p>
            </SliderSlide>
            <SliderSlide class="o-vertical-spacing">
              <h3>Dolor Sit</h3>
              <p>
                Dolor sit amet, consetetur sadipscing elitr, sed
                diam nonumy eirmod tempor invidunt ut labore et dolore magna
                aliquyam erat, sed diam voluptua. At vero eos et accusam et
                justo duo dolores et ea rebum. Stet clita kasd gubergren.
              </p>
            </SliderSlide>
          </SliderSlides>

          <div class="App__basic-example-controls">
            <button @click="prev">
              &laquo; Prev
            </button>
            <button @click="next">
              Next &raquo;
            </button>
          </div>
        </div>
      </SliderFrame>
    </section>

    <section class="App__example o-vertical-spacing o-vertical-spacing--l">
      <h2>Tabs</h2>

      <SliderFrame>
        <div slot-scope="{ activeIndex, goToIndex }">
          <ul class="App__tabs-example-tabs">
            <li>
              <button
                @click="goToIndex(0)"
                :class="{ 'is-active': activeIndex === 0 }"
                class="App__tabs-example-tab"
              >
                Tab 1
              </button>
            </li>
            <li>
              <button
                @click="goToIndex(1)"
                :class="{ 'is-active': activeIndex === 1 }"
                class="App__tabs-example-tab"
              >
                Tab 2
              </button>
            </li>
            <li>
              <button
                @click="goToIndex(2)"
                :class="{ 'is-active': activeIndex === 2 }"
                class="App__tabs-example-tab"
              >
                Tab 3
              </button>
            </li>
          </ul>

          <div class="App__tabs-example-content">
            <SliderSlides>
              <SliderSlide class="o-vertical-spacing">
                <h3>Lorem Ipsum dolor</h3>
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                  diam nonumy eirmod tempor invidunt ut labore et dolore magna
                  aliquyam erat, sed diam voluptua. At vero eos et accusam et
                  justo duo dolores et ea rebum. Stet clita kasd gubergren.
                </p>
              </SliderSlide>
              <SliderSlide class="o-vertical-spacing">
                <h3>Dolor Sit</h3>
                <p>
                  Dolor sit amet, consetetur sadipscing elitr, sed
                  diam nonumy eirmod tempor invidunt ut labore et dolore magna
                  aliquyam erat, sed diam voluptua. At vero eos et accusam et
                  justo duo dolores et ea rebum. Stet clita kasd gubergren.
                </p>
              </SliderSlide>
              <SliderSlide class="o-vertical-spacing">
                <h3>Consetetur</h3>
                <p>
                  Consetetur sadipscing elitr, sed
                  diam nonumy eirmod tempor invidunt ut labore et dolore magna
                  aliquyam erat, sed diam voluptua. At vero eos et accusam et
                  justo duo dolores et ea rebum. Stet clita kasd gubergren.
                </p>
              </SliderSlide>
            </SliderSlides>
          </div>
        </div>
      </SliderFrame>
    </section>
  </div>
</template>

<script>
import SliderFrame from './components/SliderFrame';
import SliderSlide from './components/SliderSlide.vue';
import SliderSlides from './components/SliderSlides.vue';

export default {
  name: `App`,
  components: {
    SliderFrame,
    SliderSlide,
    SliderSlides,
  },
};
</script>

<style lang="scss">
@import './assets/scss/settings/**/*';
@import './assets/scss/generic/**/*';
@import '{
  .o-container,
  .o-container--s,
} from ~@avalanche/object-container';
@import '{
  .o-vertical-spacing,
  .o-vertical-spacing--l,
  .o-vertical-spacing--xl,
} from ~@avalanche/object-vertical-spacing';

.App {
  padding-top: setting-spacing(xl);
  padding-bottom: setting-spacing(xl);

  h1 {
    text-align: center;
  }
}

.App__example {
  padding: setting-spacing(l);
  border-radius: 0.25em;
  box-shadow: 0 0.35em 1em rgba(#000, 0.2);
}

.App__basic-example-controls {
  margin-top: setting-spacing(l);
  text-align: center;
}

.App__tabs-example-tabs {
  display: flex;
}

.App__tabs-example-tab {
  padding: setting-spacing(s) setting-spacing(l);
  border: 1px solid #999;
  border-bottom: none;
  background-color: #efefef;
  cursor: pointer;
  outline: none;

  &:hover,
  &:focus,
  &.is-active {
    background-color: #999;
  }

  :not(:first-child) > & {
    border-left: none;
  }
}

.App__tabs-example-content {
  padding: setting-spacing(m);
  border: 1px solid #999;
  overflow: hidden;
}
</style>
