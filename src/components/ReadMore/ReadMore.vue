<template>
  <div class="q-pa-md row readmore">
    <q-card class="my-card" flat bordered>
      <q-img src="assets/images/readmore.png" class="readmore-img">
        <div class="d">
          <slot name="numbering"></slot>
        </div>
      </q-img>
      <q-card-section>
        <div class="readmore-title">
          <slot name="title"></slot>
        </div>
      </q-card-section>
      <div v-show="expanded">
        <q-card-section class="readmore-font">
          <div class="card-padding">
            <slot name="content"></slot>
          </div>
          <div class="readmore-padding" />
          <q-separator />
        </q-card-section>
      </div>

      <q-slide-transition>
        <q-card-actions>
          <q-space />

          <q-img
            :src="
              expanded
                ? 'assets/images/readmore-up.png'
                : 'assets/images/readmore-down.png'
            "
            @click="expanded = !expanded"
            class="readmore-btn"
          />
        </q-card-actions>
      </q-slide-transition>
    </q-card>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  data() {
    return {
      lorem:
        "To overcome the limitation of previous mass-type Metaverse platforms that only focus on the value of digital assets and transaction volumes, ERUGO WORLD aims to be the sustainable Metaverse platform which connects with reality by providing valuable services to our investors.",
    };
  },
  setup() {
    return {
      expanded: ref(false),
    };
  },
};
</script>

<style lang="scss" scoped>
.q-card--bordered {
  border: none;
}
.q-card {
  border-radius: 0;
}
.q-card__section--vert {
  padding: 0;
}
.my-card {
  width: 100%;
  max-width: 22vmax;
  margin: 0 auto;
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.16) !important;
}
.q-img__content > div {
  font-family: "S-CoreDream7";
  font-weight: 700;
  background: transparent;
}
.readmore-title {
  font-family: "S-CoreDream7";
  font-size: 0.9vmax;
  padding: 1vmax 1.5vmax 0 1.5vmax;
}
.readmore-content {
  font-family: "S-CoreDream4";
}
.card-padding {
  padding: 1vmax 1.5vmax 1.5vmax 1.5vmax;
}
.readmore-btn {
  width: 15%;
  max-width: 80px;
  text-align: center;
  cursor: pointer;
}
.row {
  display: flex;
  flex-direction: column-reverse;
}
@media screen and (max-width: 768px) {
  .readmore-btn {
    width: 40px;
  }
  .readmore-padding {
    margin-top: 5%;
  }
}
@media screen and (max-width: 768px) {
  .my-card {
    max-width: 100%;
  }
}
</style>
