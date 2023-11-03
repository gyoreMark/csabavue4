<template>
  <div class="background">
    <div class="container">
      <h1 class="text-light">KÖR</h1>
      <div class="input-group mb-3">
        <input
          type="number"
          class="form-control"
          aria-label="Recipient's username"
          aria-describedby="button-addon2"
          id="sugarInput"
          placeholder="Kör sugara (r)"
          min="1"
          v-model="sugarInput"
        />
        <button
          class="btn btn-outline-light"
          type="button"
          id="addBtn"
          @click="szamitas"
        >
          Számolás
        </button>
      </div>

      <div class="row">
        <div class="col">
          Terület
          <div class="alert alert-light" role="alert" id="">
            {{ teruletSzamitas }}
          </div>
        </div>
        <div class="col">
          Kerület
          <div class="alert alert-light" role="alert" id="">
            {{ keruletSzamitas }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      sugarInput: undefined,
      teruletSzamitas: undefined,
      keruletSzamitas: undefined,
    };
  },

  methods: {
    szamitas: function () {
      //terulet
      this.teruletSzamitas = Math.PI * Math.pow(this.sugarInput, 2);

      //kerulet
      this.keruletSzamitas = 2 * Math.PI * this.sugarInput;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.background {
  position: absolute;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  height: 100%;
  background-color: rgb(90, 61, 61);
  top: 0;
  left: 0;
  color: white;
}
</style>
