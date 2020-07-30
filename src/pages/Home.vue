<template>
  <div class="home">
    <div class="row justify-content-center">
      <h3>Modal</h3>
      <img alt="Vue logo" src="../assets/logo.png" class="logo" />
      <h3>iew</h3>
    </div>
    <div class="row buttons justify-content-center">
      <button
        type="button"
        class="btn btn-primary btn-lg"
        data-toggle="modal"
        data-target="#one"
      >Modal 1</button>
      <button
        type="button"
        class="btn btn-secondary btn-lg"
        data-toggle="modal"
        data-target="#two"
      >Modal 2</button>
      <button type="button" class="btn btn-danger btn-lg" @click="toggledOn = !toggledOn">Show Div</button>
    </div>
    <QuickModal id="one" :key="1" :modalProp="'this is my first modal'">
      <h3>This is my body</h3>
      <div slot="footer">This is my footer</div>
      <div slot="body">This is fake body slot</div>
      <div slot="title">This is my Title</div>
    </QuickModal>
    <QuickModal
      id="two"
      :dataToPass="tacos"
      :modalProp="'this is my second modal'"
    >This is different info</QuickModal>
    <div class="form-check" v-if="toggledOn">
      <label class="form-check-label">
        <input type="checkbox" class="form-check-input" name id value="checkedValue" checked />
        Display value
      </label>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import QuickModal from "../components/QuickModal";
export default {
  name: "Home",
  data() {
    return {
      toggledOn: false,
    };
  },
  computed: {
    tacos() {
      return "tims tacos";
    },
  },
  components: { QuickModal },
};
</script>

<style scoped>
.logo {
  height: 30px;
  width: 30px;
}
</style>
