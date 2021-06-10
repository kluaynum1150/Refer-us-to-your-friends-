<template>
  <b-container>
    <b-row>
      <b-col class="button-left" cols="12" sm="6">
        <!-- share buttin on Facebook -->
        <b-button
          pill
          size="lg"
          style="background:#0084ff;"
          class="mb-2 text-in-button"
          @click="shareFacebook"
        >
          <i class="lab la-facebook"></i>
          Share on Facebook
        </b-button>
      </b-col>
      <b-col class="button-right" cols="12" sm="6">
        <!-- share buttin on Facebook Messenger -->
        <b-button
          pill 
          style="background:#00c6ff;" 
          size="lg" 
          @click="shareMessenger" 
          class="mb-2 text-in-button"
        >
          <i class="lab la-facebook-messenger"></i>
          Share as Messenger
        </b-button>
      </b-col>
      <b-col class="button-left" cols="12" sm="6">
        <!-- share buttin on Line -->
        <b-button
          pill
          size="lg"
          style="background:#00c300;"
          :href="`https://social-plugins.line.me/lineit/share?url=${pageUrl}`"
          onclick="window.open(this.href, 'facebook-share','width=auto,height=auto');return false;"
          class="mb-2 text-in-button"
        >
          <i class="lab la-line"></i>
          Share as Line
        </b-button>
      </b-col>
      <b-col class="button-right" cols="12" sm="6">
        <!-- share buttin on Email -->
        <b-button
          pill
          size="lg"
          class="mb-2 text-in-button"
          :href="`mailto:?subject=I wanted you to see this site&amp;body=${pageUrl}`"
          >
          <i class="las la-envelope"></i>
          Share as Email
        </b-button>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
const FB = window.FB;
export default {
  props: ["link"],
  data() {
    return {
      pageUrl: this.link, //link for share
    };
  },
  methods: {
    // Function for share link in Facebook Messenger
    shareMessenger() {
      FB.ui({
        method: "send",
        display: "iframe",
        link: this.pageUrl,
      });
    },
    // Function for share link in Facebook feed
    shareFacebook() {
      FB.ui(
        {
          method: "share",
          display: "popup",
          href: this.pageUrl,
        },
        function () {}
      );
    },
    // Function for share link in Line
    shareLine(href){
      window.open(href, 'line-share', 'width=auto,height=auto')
      return false
    },
  },
};
</script>

<style scoped>
.aa {
  text-align: left;
}
i{
  font-size: 32px;
}
.text-in-button{
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 251px;
}
.button-left{
  display: inline-flex;
  justify-content: flex-end;
}
.button-right{
  display: inline-flex;
  justify-content: flex-start;
}
@media only screen and (max-width: 540px) {
  .button-left{
    display: inline-flex;
    justify-content: center;
  }
  .button-right{
    display: inline-flex;
    justify-content: center;
  }
}
</style>