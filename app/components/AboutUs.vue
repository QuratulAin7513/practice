<template>
  <Page>
    <ActionBar title="About Us" />
    <FlexboxLayout justifyContent="center" flexDirection="column" class="full-Height">
      <StackLayout>
        <Label
          text="SocialBu helps you manage and automate your social media."
          textWrap="true"
          padding="10"
          class="text"
        />
        <Label :text="content" textWrap="true" padding="10" class="content-text" />
      </StackLayout>

      <StackLayout>
        <FlexboxLayout alignItems="center">
          <Image
            alt="https://www.facebook.com/search/top/?q=socialBu"
            col="
                        1"
            row="0"
            horizontalAlignment="left"
            class="profile"
            src="~/assets/images/facebook.png"
          />
          <Image
            col="1"
            row="0"
            horizontalAlignment="center"
            class="profile"
            src="~/assets/images/twitter.jpg"
          />
          <Image
            col="1"
            row="0"
            horizontalAlignment="center"
            class="profile"
            src="~/assets/images/instagram.jpg"
          />
          <Image
            col="1"
            row="0"
            horizontalAlignment="right"
            class="profile"
            src="~/assets/images/linkedin.png"
          />
        </FlexboxLayout>
        <Label
          text="App Version : 1.0.0"
          textWrap="true"
          padding="10"
          class="text-bottom"
          horizontalAlignment="center"
        />
      </StackLayout>
    </FlexboxLayout>
  </Page>
</template>

<script>
export default {
  data() {
    return {
      content:
        "Spending too much time managing social media for your business? SocialBu makes it easy to manage and automate your social media "
    };
  }
};
</script>

<style>
.text {
  color: black;
  font-size: 17;
  font-style: italic;
  font-weight: bold;
  margin-top: 1;
  horizontal-align: center;
}

.text-bottom {
  color: black;
  font-size: 12;

  margin-left: 10;
  margin-bottom: 1;
  horizontal-align: center;
}

.content-text {
  color: #576666;
  font-size: 11;

  margin-top: 3;
  horizontal-align: center;
}

.profile {
  border-width: 3;
  border-color: #dae0e0;
  background-color: #f1ebeb;
  border-radius: 40;
  margin-top: 15;

  width: 60;
  height: 60;
}

.full-Height {
  height: 100%;
}
</style>