<template>
  <page actionBarHidden="true" backgroundSpanUnderStatusBar="true">
    <!-- @loaded="onLoaded" -->

    <GridLayout rows="auto,auto,*,auto" columns="auto">
      <GridLayout
        row="0"
        ref="navStatusBar"
        class="navStatusBar"
        backgroundColor="#50C7C7"
        verticalAlignment="top"
        height="60"
        width="100%"
        rows="auto"
        columns="*,auto,auto,auto"
      >
        <Label col="0" row="0" text="Posts" class="status-title"></Label>
        <Image
          col="1"
          row="0"
          @tap="search"
          horizontalAlignment="right"
          class="status-img"
          src="~/assets/images/search.png"
        />
        <Image
          col="2"
          row="0"
          @tap="bell"
          horizontalAlignment="right"
          class="status-img"
          src="~/assets/images/bell.png"
        />
        <Image
          horizontalAlignment="right"
          stretch="aspectFill"
          col="3"
          row="0"
          class="status-profile"
          src="~/assets/images/me.jpg"
        />
      </GridLayout>

      <GridLayout v-show="selectedTabview == 0" row="2" width="100%" backgroundColor="white">
        <ListView ref="listview" separatorColor="transparent" for="item in items" :key="index">
          <v-template>
            <item :item="item" @clicked="showItem(item)" />
          </v-template>
        </ListView>
      </GridLayout>
    </GridLayout>
  </page>
</template>
<script>
import { isIOS, isAndroid } from "tns-core-modules/platform";
import navBottom from "./custom/navBottom";
import Item from "./custom/item";
import ItemDetails from "./ItemDetails";
const gestures = require("ui/gestures");
const app = require("application");

export default {
  components: {
    navBottom,
    Item
  },
  data() {
    return {
      lastDelY: 0,
      headerCollapsed: false,
      selectedTab: 0,
      selectedTabview: 0,
      items: [
        {
          name: "Save time by scheduling posts",
          cover: "~/assets/images/pic1.png",

          category: "PUBLISH",

          price: "300.00",
          likes: 987,
          isLike: false,
          isFavorite: true,
          comments: 13,
          rating: "4.5",
          description:
            "Schedule and publish content across all your social networks in one place.No matter how many social media profiles you manage, this is always going to be easy with SocialBu."
        },
        {
          name: "All your conversations in one place",
          cover: "~/assets/images/pic2.png",
          category: "RESPOND",

          price: "230.00",
          likes: 891,
          isLike: true,
          isFavorite: true,
          comments: 7,
          rating: "4.0",
          description:
            "Respond to your messages, posts, and comments from within SocialBu.No need to switch between different social networks again and again to keep up with your followers."
        },
        {
          name: "Listen to what they say about you",
          cover: "~/assets/images/pic3.png",
          category: "MONITOR",
          price: "300.00",
          likes: 730,
          isLike: true,
          isFavorite: true,
          comments: 11,
          rating: "4.0",
          description:
            "People talk a lot. Monitor your social media and listen to what they have to say about you or topics concerning you.Never miss an opportunity to jump in."
        },
        {
          name: "Truly automate your social media",
          cover: "~/assets/images/pic4.png",
          category: "AUTOMATE",
          price: "300.00",
          likes: 730,
          isLike: true,
          isFavorite: true,
          comments: 11,
          rating: "4.0",
          description:
            "Automate multiple scenarios and eliminate tedious tasks. The possibilities are endless.It's no fun to do one simple thing again and again for everyone."
        },
        {
          name: "Detailed insights for your social media",
          cover: "~/assets/images/pic5.png",
          category: "ANALYZE",
          price: "300.00",
          likes: 730,
          isLike: true,
          isFavorite: true,
          comments: 11,
          rating: "4.0",
          description:
            "Analyze your social media performance in detail and see how you can improve it"
        },
        {
          name: "Work as a team",
          cover: "~/assets/images/pic6.png",
          category: "TEAM COLLABORATION",
          price: "300.00",
          likes: 730,
          isLike: true,
          isFavorite: true,
          comments: 11,
          rating: "4.0",
          description:
            "Collaborate and manage your social media as a team.Together, you can move mountains!"
        }
      ]
    };
  },
  methods: {
    search() {
      console.log("search");
    },
    bell() {
      console.log("bell");
    },
    showItem(payload) {
      this.$navigateTo(ItemDetails, {
        props: {
          item: payload
        },
        animated: true,
        transition: {
          name: "slideTop",
          duration: 380,
          curve: "easeIn"
        }
      });
    }
  }
};
</script>

<style>
.tabview.active {
  border-bottom-color: white;
  border-bottom-width: 3;
  margin: 0;
  height: 50;
}

.tabviewText {
  margin-top: 15;
  margin-bottom: 5;
  font-size: 13;
  color: #d8d2d2;
  horizontal-align: center;
}

.navTab {
  background-color: #bd2122;
}

.navTabview {
  background-color: blue;
}

.status-img {
  margin-top: 4;
  margin-right: 20;
  width: 30;
  height: 30;
}

.status-profile {
  border-width: 1;
  border-color: #ffffff;
  background-color: #f1ebeb;
  border-radius: 50%;
  margin-top: 4;
  margin-right: 15;
  width: 30;
  height: 30;
}

.status-title {
  color: white;
  font-size: 18;
  margin-left: 15;
  margin-top: 8;
  horizontal-align: left;
  vertical-align: center;
}
</style>