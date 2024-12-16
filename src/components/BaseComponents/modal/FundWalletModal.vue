<template>
  <div>
    <div class="backdrop"></div>
    <dialog open>
      <form class="alpha" @submit.prevent="authenticate">

        <div class="first-part">
          <i class='bx bx-x' @click="close"></i>
        </div>
        <div class="second-part">
          <p class="text-1">Authenticate Certificate</p>
          <p class="text-2">How to authenticate your Certificate:</p>
          <p class="text-3">Insert your certificate number below.</p>


          <input type="text" v-model="text" required class="input"/>
        </div>


        <br/>
        <button   style="background-color: #0669f2;border: 1px solid #0669f2;">
          <span v-if="loading === false" >Authenticate</span>
          <span v-if="loading === true" class="loader"></span>

        </button>


      </form>

    </dialog>
  </div>
</template>

<script>

import Toastify from 'toastify-js'
import 'toastify-js/src/toastify.css'
export default {
  name: "FundWalletModal",
  emits: ['close', 'open'],
  data() {
    return {
      contacts: [],
      accountNumber: '',
      bankName: '',
      bitcoinAddress: '',
      ethereumAddress: '',
      routingNumber: '',
      loading: false,
      text: "",
    };
  },
  components: {

  },
  props: {
    selectedItem: {
      type: Object,
      default: null
    }
  },
  computed:{

  },
  methods:{
    async close() {
      this.$emit('close');
      // await Swal.fire({
      //   icon: 'success',
      //   title: 'Pending',
      //   text: 'Deposit Request Pending',
      // });
    },

    authenticate() {
      this.loading = true; // Start loading
      setTimeout(() => {
        this.loading = false; // Stop loading after 10 seconds

        // Check if the entered certificate number is valid
        if (this.text === '20170203001' || this.text === '987654321') {
          this.$emit('close');
          this.$emit('open');
        } else {
          this.showErrorToast('Invalid Certificate Number'); // Show error toast
        }

        // Reset the input field and close the modal
        this.text = '';
        this.close();
      }, 10000); // 10000 milliseconds = 10 seconds
    },

    showToast(message, backgroundColor) {
      Toastify({
        text: message,
        duration: 3000,
        close: true,
        gravity: 'top', // `top` or `bottom`
        position: 'right', // `left`, `center`, or `right`
        backgroundColor: backgroundColor,
        stopOnFocus: true, // Prevents dismissing of toast on hover
        onClick: function() {} // Callback after click
      }).showToast();
    },

    showErrorToast(message) {
      Toastify({
        text: message,
        duration: 3000,
        close: true,
        gravity: 'top', // `top` or `bottom`
        position: 'center', // `left`, `center`, or `right`
        backgroundColor: '#f44336', // Error red background
        stopOnFocus: true, // Prevents dismissing of toast on hover
        onClick: function() {} // Callback after click
      }).showToast();
    }

    // authenticate() {
    //   this.loading = true; // Start loading
    //   setTimeout(() => {
    //     this.loading = false; // Stop loading after 10 seconds
    //     this.text = ""
    //     this.showToast();
    //     this.close()
    //   }, 10000); // 10000 milliseconds = 10 seconds
    // },
    // showToast() {
    //   Toastify({
    //     text: "Document is Authentic",
    //     duration: 3000,
    //     close: true,
    //     gravity: "top", // `top` or `bottom`
    //     position: "right", // `left`, `center` or `right`
    //     backgroundColor: "#39a539",
    //     stopOnFocus: true, // Prevents dismissing of toast on hover
    //     onClick: function(){} // Callback after click
    //   }).showToast();
    // }
  },
  created() {

  },

  mounted() {

  }
}
</script>


<style scoped >

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: 10;
  background-color: rgba(0, 0, 0, 0.7);
}


dialog {
  position: fixed;
  top: 10vh;
  width: 32rem;
  height: 32rem;
  left: calc(50% - 17rem);
  margin: 0;
  background-color: transparent;
  z-index: 100;
  border: none;
  animation: modal 0.3s ease-out forwards;
}

.alpha{
  position: relative;
  display: block;
  overflow: hidden;
  width: 500px;
  height: 350px;
  /*height: auto;*/
  padding: 24px;
  border-radius: 5px;
  background-color: #ffffff;
  border: 0.5px solid #3C4A57FF;
  box-shadow: 0 0 34px 0 rgba(3, 28, 67, 0.13);
}

.first-part{
  display: flex;
  justify-content: space-between;
}

.bx-x{
  font-size: 25px;
  padding-top: 2px;
  color: #0f171c;
}

.bx-objects-horizontal-left{
  font-size: 25px;
  padding-top: 2px;
  color: #0f171c;
}

.text-1{
  font-weight: 600;
  font-size: 18px;
  line-height: 28px;
  color: #0f171c;
  padding-top: 2.5%;
  padding-bottom: 0.5%;
}

.text-2{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #0f171c;
  padding-top: 1%;
  padding-bottom: 0.5%;
}

.text-3{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #0f171c;
  padding-top: 1.5%;
  padding-bottom: 2%;
}

.text-4{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #0f171c;
  padding-top: 1.5%;
  padding-bottom: 1.5%;
}

.text-5{
  font-weight: 400;
  font-size: 15px;
  line-height: 24px;
  color: #0f171c;
  padding-top: 2%;
  padding-bottom: 2%;
  word-wrap: break-word; /* or overflow-wrap: break-word; */
}

button{
  padding: 8px 55px;
  color: white;
  background-color: #0f171c;
  border: 0.5px solid #3C4A57FF;
  border-radius: 5px;
  font-size: 13px;
  text-decoration: none;
  width: 100%;
  /*display: block;*/
  /*margin-left: auto;*/
  /*margin-right: auto;*/
}

.input{
  width: 100%;
  margin-top: 10px;
  padding: 5px 20px;
  border-radius: 5px;
  border: 0.5px solid #5b9fff;
}


@keyframes modal {
  from {
    opacity: 0;
    transform: translateY(-50px) scale(0.9);
  }

  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}


.loader {
  width: 20px;
  height: 20px;
  border: 2.5px solid #ffffff;
  border-bottom-color: transparent;
  border-radius: 50%;
  display: inline-block;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
}

@keyframes rotation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.seprate{
  display: flex;
  align-items: center;
  align-content: center;
  margin-top: 20px;
  margin-bottom: 10px;
  justify-content: center;
  width: 100%;
  margin-left: auto;
  margin-right: auto;
}

@media (max-width: 500px) {
  dialog {
    top: 11vh;
    width: 25rem;
    height: 18rem;
    left: calc(50% - 11rem);
    right: 30px;
  }
  .alpha{
    width: 360px;
    height: 320px;
  }
  h3{
    font-size: 18px;
  }
  p{
    font-size: unset;
  }

  .text-1{
    font-size: 17px;
    line-height: 26px;
    padding-top: 2%;
  }

  .text-2{
    font-size: 15px;
    line-height: 22px;
    padding-top: unset;
    padding-bottom: unset;
  }

  .text-3{
    font-size: 15px;
    line-height: 22px;
    padding-top: 1%;
    padding-bottom: 1%;
  }

  .text-4, .text-5, .text-6{
    font-size: 15px;
    line-height: 22px;
    padding-top: 1%;
    padding-bottom: 1%;
  }

}
</style>