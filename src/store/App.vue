<template>
  <div class="d-flex justify-content-center align-items-center flex-column vh-100">
    <div class="counter bg-dark p-4">
      <div class="row">
        <div class="col-md-5 mx-auto">
          <div class="form">
            <div>
              <input type="text" class="form-control text-center font-weight-bold" placeholder="0" readonly :value="counter">
            </div>
            <div class="row mt-3">
              <div class="col">
                <button @click.prevent="increase" class="btn btn-outline w-100 mb-2">
                  Increase
                </button>
                <button @click.prevent="decrease" class="btn btn-outline w-100">
                  Decrease
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  computed: {
    counter() {
      return this.$store.state.counter
    }
  },
  methods: {
    increase(){
      this.$store.dispatch('increaseCounter')
    },
    decrease(){
      this.$store.dispatch('decreaseCounter')
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body{
  background-image: url(https://i.postimg.cc/SNwXDTxv/pexels-irina-iriser-1005715.jpg);
}

.counter {
  max-width: 500px;
  width: 100%;
}

.btn{
    color: #9EA1D4 !important;
    border-color:#9EA1D4 !important;
    background-color: transparent;
}
.btn:hover{
    color: #FD8A8A !important;
    border-color:#FD8A8A !important;
    background-color: transparent;
}

@media (max-width: 767.98px) {
  .counter {
    max-width: none;
    margin: 0 16px;
  }
}
</style>
