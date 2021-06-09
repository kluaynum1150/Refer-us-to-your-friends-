<template>
  <div class="about">
    <b-button @click="shareFace">gg</b-button>
    <a
      href="fb-messenger://share/?link= https%3A%2F%2Fdevelopers.facebook.com%2Fdocs%2Fsharing%2Freference%2Fsend-dialog&app_id=492095872116370"
      >Send In Messenger</a
    >
    <!-- <div class="fb-share-button" data-href="https://www.raymondcamden.com/2020/03/04/vue-quick-shot-copy-to-the-clipboard" data-layout="button" data-size="large"><a target="_blank" href="https://www.facebook.com/sharer/sharer.php?u=https%3A%2F%2Fwww.raymondcamden.com%2F2020%2F03%2F04%2Fvue-quick-shot-copy-to-the-clipboard&amp;src=sdkpreparse" class="fb-xfbml-parse-ignore">แชร์</a></div> -->
    <!-- <iframe :src="`https://www.facebook.com/plugins/share_button.php?href=${pageUrl}&layout=button&size=large&appId=492095872116370&width=69&height=28`" width="69" height="28" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share"></iframe> -->
    <h1>This is an about page</h1>
    <b-button
      size="lg"
      variant="primary"
      :href="`https://www.facebook.com/sharer/sharer.php?u=${pageUrl}`"
      class="mb-2"
      onclick="window.open(this.href, 'facebook-share','width=auto,height=auto');return false;"
    >
      <b-icon icon="facebook" aria-label="Help"></b-icon>
    </b-button>
    <b-button
      size="lg"
      variant="primary"
      :href="`https://www.facebook.com/dialog/send?app_id=492095872116370&display=popup&link=${pageUrl}&utm_medium=facebook_messenger&utm_source=socialnetwork&redirect_uri=https%3A%2F%2Fwww.shareaholic.com%2Fshare%2Fthanks`"
      onclick="window.open(this.href, 'facebook-share','width=auto,height=auto');return false;"
      class="mb-2"
    >
      <b-icon-facebook aria-label="Help"></b-icon-facebook>
    </b-button>
    <b-button
      size="lg"
      variant="primary"
      :href="`https://social-plugins.line.me/lineit/share?url=${pageUrl}`"
      class="mb-2"
    >
      <b-icon-link aria-label="Help"></b-icon-link>
    </b-button>
    <a
      href="mailto:?subject=I wanted you to see this site&amp;body=Check out this site http://www.website.com."
      title="Share by Email"
    >
      <img
        src="http://png-2.findicons.com/files/icons/573/must_have/48/mail.png"
      />
    </a>

    <!-- <v-btn dark fab bottom color="blue" small :href="`https://www.facebook.com/sharer/sharer.php?u=${pageUrl}`" target="_blank">
          <v-icon>mdi-facebook</v-icon>
        </v-btn> -->

    <!-- <b-button @click="shareFace" variant="success">Share to Facebook</b-button> -->
    <!-- <b-button @click="shareFace" variant="success">Share to Facebook</b-button> -->
    <!-- <ShareNetwork
    network="facebook"
    url="https://news.vuejs.org/issues/180"
  >
    <b-button variant="success">Share on Facebook</b-button>
</ShareNetwork>
<ShareNetwork
    network="messenger"
    url="https://news.vuejs.org/issues/180"
  >
    <b-button variant="success">Share on Messenger</b-button>
</ShareNetwork>
<ShareNetwork
    network="line"
    url="https://news.vuejs.org/issues/180"
  >
    <b-button variant="success">Share on Line</b-button>
</ShareNetwork>
<ShareNetwork
    network="email"
    url="https://news.vuejs.org/issues/180"
  >
    <b-button variant="success">Share on Email</b-button>
</ShareNetwork> -->
    <Refer v-bind:link="pageUrl" />
  </div>
</template>

<script>
import Refer from "@/components/buttonShare.vue";
const FB = window.FB;
export default {
  name: "About",
  components: {
    Refer,
  },
  data() {
    return {
      pageUrl:
        "https://medium.com/@newnoi/%E0%B8%A1%E0%B8%B2%E0%B8%AA%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%87-chatbot-%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B9%84%E0%B8%97%E0%B8%A2%E0%B9%86-%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2-machine-learning-lstm-model-%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%94%E0%B8%B5%E0%B8%81%E0%B8%A7%E0%B9%88%E0%B8%B2-part1-6230eac8d1f8",
    };
  },
  methods: {
    shareFace() {
      FB.ui(
        {
          method: "share",
          display: "touch",
          href: "https://www.raymondcamden.com/2020/03/04/vue-quick-shot-copy-to-the-clipboard",
        },
        function () {}
      );
    },
  },
};
</script>