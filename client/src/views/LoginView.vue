<script>
import { mapActions } from "pinia";
import { GoogleLogin } from "vue3-google-login";
import { useCounterStore } from "../stores/counter";

export default {
  name: "LoginView",
  components: { GoogleLogin },
  methods: {
    ...mapActions(useCounterStore, ["handleGoogleLogin"]),
  },
};
</script>

<template>
  <!-- Start Login -->
  <section
    id="login-section"
    class="vh-100 bg-image"
    style="
      background-image: url('https://assets.mocomuseum.com/images_prod/exhibition/_2048x1536_crop_center-center_none/2162/UNTITLED-2015-244CM-HR-IMAGE.webp');
    "
  >
    <div class="mask d-flex align-items-center h-100 gradient-custom-3">
      <div class="container h-100">
        <div class="row d-flex justify-content-center align-items-center h-100">
          <div class="col-12 col-md-9 col-lg-7 col-xl-6">
            <div
              class="card bg-image"
              style="
                background-image: url('https://i.postimg.cc/d1P4MRgj/log.png');
              "
            >
              <div class="card-body p-5">
                <h1
                  class="text-uppercase text-center mb-5"
                  style="color: #c7110d"
                >
                  <img src="../assets/neko.svg" alt="logo" height=" 80" />

                </h1>


                <div class="d-flex justify-content-center mt-3 mb-0">
                  <p>Sign in with Google Account</p>
                </div>
                <div class="d-flex justify-content-center">
                  <GoogleLogin :callback="handleGoogleLogin" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- End Login -->
</template>
