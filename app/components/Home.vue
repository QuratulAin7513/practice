<template>
  <Page actionBarHidden="true">
    <GridLayout rows="auto,auto,*,auto" columns="auto" height="2000px">
      <RadSideDrawer ref="drawer">
        <StackLayout ~drawerContent backgroundColor="#50C7C7" height="2000px">
          <StackLayout height="120" class="backImage">
            <Image
              col="1"
              row="0"
              horizontalAlignment="left"
              class="profile"
              src="~/assets/images/me.jpg"
            />
            <Label text="Qurat-Ul-Ain" class="title" />
            <FlexboxLayout>
              <Label text="734 Followers" class="followers" />
              <Label
                col="1"
                row="0"
                class="fa fas-users icon"
                :text="'fa-users' | fonticon"
                fontSize="
					                        10px"
                color="#FFFFFF"
                isIconSizeFixed="true"
              />
            </FlexboxLayout>
          </StackLayout>
          <StackLayout>
            <Label text="Profile" padding="10" backgroundColor="lightgray" />
            <Label text="Message" padding="10" />
            <Label text="All Posts" padding="10" @tap="goToPostsPage" />
            <Label text="Activities" padding="10" backgroundColor="lightgray" />
            <Label text="History" padding="10" />
            <Label text="About Us" padding="10" @tap="goToAboutUsPage" />
            <Label text="Drafts" padding="10" />
            <Label text="Sign Out" padding="10" />
          </StackLayout>
          <Label
            text="Close"
            color="lightgray"
            padding="10"
            style="horizontal-align: center"
            @tap="onCloseDrawerTap"
          />
        </StackLayout>
        <StackLayout ~mainContent>
          <Label
            col="1"
            row="0"
            class="fa fas-list-ul"
            :text="'fa-list-ul' | fonticon"
            color="#50C7C7"
            fontSize="40px"
            isIconSizeFixed="true"
            style="horizontal-align: left"
            @tap="onOpenDrawerTap"
          />
          <image src="~/assets/images/logo.png" class="logo-container"> </image>
          <Label
            text="SocialBu helps you manage and automate 
                    your social media."
            textWrap="true"
            fontSize="13"
            padding="10"
            class="center-text"
          />
        </StackLayout>
      </RadSideDrawer>
    </GridLayout>
  </Page>
</template>

<script>
import Vue from "nativescript-vue";
import Posts from "./Posts";
import AboutUs from "./AboutUs";
import RadSideDrawer from "nativescript-ui-sidedrawer/vue";
Vue.use(RadSideDrawer);

export default {
  methods: {
    onOpenDrawerTap() {
      this.$refs.drawer.nativeView.showDrawer();
    },
    onCloseDrawerTap() {
      this.$refs.drawer.nativeView.closeDrawer();
    },
    goToAboutUsPage() {
      this.$navigateTo(AboutUs);
    },
    goToPostsPage() {
      this.$navigateTo(Posts);
    }
  },

  data() {
    return {
      mainContentText:
        "SocialBu helps you manage and automate your social media."
    };
  }
};
</script>

<style>
.backImage {
  background-image: url("~/assets/images/backgroundImage.jpg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.logo-container {
  width: 150;
  margin-bottom: 60;
}

.title {
  color: white;
  font-size: 14;
  font-weight: bold;
  margin-left: 5;
  margin-top: 5;
  horizontal-align: left;
  vertical-align: center;
}

.icon {
  margin-top: 1;
  margin-left: 10;
}

.center-text {
  vertical-align: center;
  text-align: center;
  font-size: 40;
  margin-right: 10;
  padding: 10;
}

.followers {
  color: white;
  font-size: 10;
  margin-left: 5;
  margin-top: 1;
  horizontal-align: left;
  vertical-align: center;
}

.profile {
  border-width: 3;
  border-color: #ffffff;
  background-color: #f1ebeb;
  border-radius: 40;
  margin-top: 15;
  margin-left: 15;
  width: 60;
  height: 60;
}
</style>
