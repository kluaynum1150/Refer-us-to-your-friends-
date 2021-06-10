<template>
  <div class="home">
    <b-container class="body-box" style="width: 90%; height: 40em">
      <center><img src="../assets/logo_megaphone.png" class="image"></center>
      <h2 style="padding: 10px">Refer us to your friends!</h2>
      <!-- text inputs and clipboard button -->
      <center>
        <b-input-group class="input-link">
          <b-form-input v-model="url" disabled></b-form-input>
          <b-input-group-append>
            <b-button
              v-b-tooltip.hover="tooltipText"
              variant="outline-success"
              @click="copy(url)"
            >
              <i class="lar la-clipboard"></i>
            </b-button>
          </b-input-group-append>
        </b-input-group>
      </center>
      <!-- Show share button -->
      <ShareButton v-bind:link="url" />
    </b-container>
  </div>
</template>

<script>
import ShareButton from "@/components/buttonShare.vue";
export default {
  name: "Home",
  components: {
    ShareButton,
  },
  data() {
    return {
      url: "https://www.facebook.com/nattapon.tongta", //My Facebook Profile
      tooltipText: "copy link!"
    };
  },
  methods: {
    // Function for copy link in text inputs
    async copy(link) {
      this.tooltipText = "Copied!"
      await navigator.clipboard.writeText(link);
      setTimeout(() => {
        this.tooltipText = "copy link!"
      }, 1000);
    },
  },
};
</script>

<style scoped>
.home{
  padding-block-start: 0.5em;
  align-content: center;
}
.input-link {
  width: 70%;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  padding: 25px 0px 45px;
}
.body-box {
  border-style: solid;
  border-radius: 10px;
  align-items: center;
  display: grid;
  justify-content: center;
}
i{
  font-size: 16px;
}
.image{
  height: 5em;
}
</style>