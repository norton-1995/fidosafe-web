<template>
  <b-container>
    <b-row>
      <b-col class="mt-5">
        <h2>Create a Fidosafe</h2>
        <p class="lead mt-3">
        We'll transfer you to our DeBot to create a safe. Once the safe is complete, you will navigate back to the website to further manage your safe.
        </p>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
          <div class="d-flex justify-content-center">
            <div>
              <img src="../assets/add-safe.svg" alt=""/>
            </div>
          </div>
      </b-col>
    </b-row>
    <b-row>
      <b-col class="d-flex justify-content-center">
        <b-button variant="primary" size="lg" v-on:click="createSafe()">Create</b-button>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import { DebotContractApi } from "../api/DebotContractApi";

export default {
    name: 'Home',
        methods: {
            createSafe() {
              this.$store.commit('Confirmation/sendConfrimation', DebotContractApi.getCreateSafeData(this.debotAccount.address));
            }
        },
    components: {
    }
}
</script>
<style lang="less" scoped>
.safe-img {
  background-image: url("../assets/add-safe.svg");
  background-repeat: no-repeat;
  background-position: center;
  width: 20vw;
  height: 20vh;
}
</style>