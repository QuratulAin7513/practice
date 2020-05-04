<template>
    <Page actionBarHidden="true" class="coverImage">
        <FlexboxLayout justifyContent="center" flexDirection="column"
            class="full-Height">
            <image src="~/assets/images/logo-icon.png" class="logo-container">
            </image>
            <StackLayout class="container">
                <FlexboxLayout alignItems="center" class="border-bottom">
                    <Label col="1" row="0" class="fa fas-user"
                        :text="'fa-user' | fonticon" color="#FFFFFF"
                        fontSize="20px" isIconSizeFixed="true" />
                    <TextField v-model="usernameInput" hint="Username"
                        class="input"></TextField>
                </FlexboxLayout>
                <FlexboxLayout alignItems="center" class="border-bottom">
                    <Label col="1" row="0" class="fa fas-lock"
                        :text="'fa-lock' | fonticon" fontSize="
                        20px" color="#FFFFFF" isIconSizeFixed="true" />
                    <TextField v-model=" passwordInput" hint="Password"
                        class="input" secure="true">
                    </TextField>
                </FlexboxLayout>
                <Button text="Login" @tap="goToHomePage" class="my-button" />
                <FlexboxLayout alignItems="center"
                    justifyContent="space-between" class="auth-buttons">
                    <label horizontalAlignment="left" text="Create Account">
                    </label>
                    <label horizontalAlignment="right" text="Forgot Password">
                    </label>
                </FlexboxLayout>
            </StackLayout>
        </FlexboxLayout>


    </Page>
</template>

<script>
    import Home from "./Home";
    export default {
        data() {
            return {
                textFieldValue: "",

                usernameInput: "",
                passwordInput: ""
            };
        },
        methods: {
            goToHomePage() {
                this.$navigateTo(Home);
            }
        }
    };
</script>

<style>
    .border-bottom {
        border-bottom-width: 1;
        border-bottom-color: white;
        margin-bottom: 40;
        padding-bottom: 8;
    }

    .input {
        placeholder-color: rgb(191, 186, 186);
        border-bottom-color:text-transform;
        color: white;
    }

    .icon-margin {
        margin-right: 10;
        color: white;
    }

    .my-button {
        background-color: #4bd5dc;
        color: white;
        font-weight: bold;
        border-radius: 25;
        padding-bottom: 14;
        padding-top: 14;
        text-transform: uppercase;
        letter-spacing: 0.1;
        margin-bottom: 20;
        margin-top: 10;
    }

    .auth-buttons {
        color: white;
        font-size: 14;
    }

    .full-Height {
        height: 100%;
    }

    .logo-container {
        width: 150;
        margin-bottom: 60;
    }

    .container {
        margin-right: 34;
        margin-left: 34;
    }

    .coverImage {
        background-image: url("~/assets/images/backgroundImage.jpg");
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
    }
</style>