<template>
  <div class="alpha">
    <div class="the-footer">


      <div class="bottom">
        <div class="logo-container">


          <div class="footer-link-container">
<!--            <h3 class="footer-title">Personal Bio.</h3>-->
<!--            <p class="footer-link width">Crafting Exotic Experiences.</p>-->
            <div class="social-part-1" style="margin-top: 2%">
              <p class="text-1">Privacy Policy</p>
              <p class="text-1">Terms & Conditions</p>
              <p class="text-1">Powered by Nucleus</p>
            </div>

            <div class="social-part-1" style="margin-top: 2%">
              <img src="https://certifaction.com/wp-content/uploads/2021/03/iso-certified-solution.png" alt="" class="image-4" />
              <img src="https://certifaction.com/wp-content/uploads/2024/10/zertes.svg" alt="" class="image-4" />
              <img src="https://certifaction.com/wp-content/uploads/2024/10/dsgvo.svg" alt="" class="image-4" />
              <img src="https://certifaction.com/wp-content/uploads/2021/04/iso.svg" alt="" class="image-4" />
            </div>

<!--            <div class="social-part-1" style="margin-top: 2%">-->
<!--              <p-->
<!--                  style="margin-top: 1%;font-family: 'BR-Firma-Bold', sans-serif;"-->
<!--                  class="text-1">-->
<!--                Contact us : omarfahaduae07@gmail.com-->
<!--              </p>-->
<!--            </div>-->


          </div>

        </div>
      </div>
      <hr/>

      <div class="copyright">
        <p style="padding-bottom: 7px;" class="text-1">
          Electronic signatures for SecureCertify are legally valid and meet the strictest legal requirements of
          Switzerland, the EU and all major global standards (incl. eIDAS, ZertES, UETA, ESIGN).
        </p>
        <p style="padding-bottom: 5px;" class="text-1">© 2024 SecureCertify.com</p>
      </div>
    </div>
  </div>
</template>

<script>



export default {
  name: 'FooterHome2',
  methods: {
      loadJivoWidget() {
        // Check if the script is already loaded to avoid duplicate script tags
        if (!document.querySelector(`script[src="//code.jivosite.com/widget/Xq2ozE05eq"]`)) {
          // Create a new script tag
          const script = document.createElement('script');
          script.src = "//code.jivosite.com/widget/Xq2ozE05eq";
          script.async = true;

          // Append the script tag to the document body
          document.body.appendChild(script);
        }
      },
    onPostClick() {
      this.$router.push("/");
      window.scrollTo(0, 0);
    },
    onPostClick2() {
      this.$router.push("/login");
      window.scrollTo(0, 0);
    },
    onPostClick3() {
      this.$router.push("/register");
      window.scrollTo(0, 0);
    },
    onPostClick4() {
      this.$router.push("/faq");
      window.scrollTo(0, 0);
    },
    onPostClick5() {
      this.$router.push("/contact");
      window.scrollTo(0, 0);
    },
  },
}
</script>

<style scoped>
.contain{
  width: 90%;
}
.the-footer {
  background: #14213d !important;
  color: #ccc;
  padding: 1.5vh  1vh;
}

.social-part-1{
  display: flex;
  gap: 15px;
}

.logo-container {
  display: flex;
  justify-content: space-between;
  margin-left: 5%;
  /*margin-right: 7%;*/
  padding-top: 1%;
}

.footer-title {
  font-size: 20px;
  line-height: 20px;
}

.image-4{
  width: 15%;
}

.footer-link {
  display: block;
  font-size: 16px;
  line-height: 25px;
  opacity: 0.8;
  padding-top: 10px;
  color: #ffffff;
}

.bottom{
  margin-top: 2%;
}

.footer-link-container {
  width: 40%;
  text-align: left;
}

.footer-link-container2{
  /*padding-right: 5%;*/
}
.stay-connected{

}
.socials-container {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  padding-top: 20px;
  width: 100%;
}

hr {
  color: #ffffff;
  width: 100%;
  background-color: #ffffff;
  border: 0.5px solid #ffffff;
  opacity: 0.2;
  margin-top: 20px;
  margin-bottom: 20px;
}

.copyright {
  font-size: 13px;
  line-height: 19px;
  opacity: 0.75;
  margin-top: 10px;
  padding-bottom: 0;
  margin-bottom: 0;
  color: #ffffff;
  font-weight: 900;
  width: 65%;
  margin-left: 5%;
}
.footer-img {
  width: 22%;
}
a {
  text-decoration: none;
  color: #ffffff;
  transition: ease 0.3s;
}
a:hover{
  color: #ffffff;
  font-weight: 700;
}

.bit{
  margin-bottom: 25px;
}
.bx {
  font-size: 27px;
}
.bx-mail-send{
}
.last-div{
  display: flex;
  margin-bottom: 15px;
}
.last-div-para{
  font-size: 15px;
  padding-left: 10px;
  line-height: 1.3;
  color: #ffffff;
}
.footer-title{
  color: #ffffff;
  /*font-size: 30px;*/
  font-weight: bold;
}

.google{
  width: 40%;
  margin-left: 2%;
  margin-top: 3%;
}

.social-part-1 i {
  padding-right: 10px;
  margin-top: 1%;
}

img{
  width: 85%;
  padding-right: 20px;
}

a{
  width: 100%;
}

.section-part{
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  padding-top: 30px;
  padding-bottom: 15px;
  padding-left: 2%;
  /*background: #393939;*/
  margin-top: 2%;
  margin-bottom: 1.5%;
}


@media (max-width: 990px) {
  .footer-link-container {
    margin-left: 2%;
    margin-right: 3%;
    width: 80%;
  }
}
@media (max-width: 760px) {
  .bottom {
    display: block;
    align-content: center;
    text-align: center;
  }
  .footer-container {
    display: block;
    align-content: center;
    text-align: center;
  }
  .the-footer {
    margin-top: unset;
  }
  .footer-img {
    width: 50%;
    min-width: unset;
    border-radius: 20px;
    margin-bottom: 20px;
  }
  .footer-link-container {
    margin-left: unset;
    margin-right: unset;
    width: unset;

    margin-top: 3%;
  }
  .footer-link-container2 {
    margin-bottom: 10%;
    margin-top: 10%;
  }
  .last-div{
    margin-right: 10%;
    margin-bottom: unset;
  }
  .copyright{
    font-size: 17px;
  }
}
@media (max-width: 700px) {

  .text-1{
    font-size: 13px;
  }

  .last-div-para{
    text-align: left;
  }
  img{
    width: 100%;
    padding-bottom: 6%;
    padding-right: 20px;
  }
  h1{
    font-size: 25px;
  }
  .footer-link-container {
    margin-left: unset;
    margin-right: unset;
    width: unset;
  }
  .footer-link {
    display: block;
    font-size: 15px;
  }
  .footer-title {
    font-size: 18px;
    padding-bottom: unset;
  }

  .footer-img {
    width: 50%;
    display: block;
    margin-right: auto;
    margin-left: auto;
  }
  .copyright {
    font-size: 13px;
    opacity: 0.8;
    width: 90%;
  }
  .bx{
    font-size: 25px;
  }
  .last-div-para{
    font-size: 16px;
    padding-left: 8px;
  }
  .logo-container {
    display: flex;
    flex-direction: column;
    padding-top: 2%;
  }
  .google{
    width: 45%;
  }

}
@media (max-width: 500px) {
  .copyright{
    font-size: 12px;
  }
  img{
    width: 42%;
    display: block;
    margin-right: auto;
    margin-left: auto;
    padding-bottom: 6%;
  }

  .section-part{
    display: flex;
    justify-content: center;
    flex-direction: column;
    margin-left: unset;
    padding-bottom: 5px;
  }


  .logo-container {
    margin-left: unset;
  }
}
</style>