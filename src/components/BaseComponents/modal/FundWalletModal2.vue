<template>
  <div >
    <div class="backdrop"  @click="close"></div>
    <dialog open>
      <div class="alpha" @click.stop>

        <div class="first-part">
<!--          <img src="@/assets/fund-wallet-icon.svg" alt="fund-wallet-icon"/>-->
          <i class='bx bx-x' @click="close"></i>
        </div>

        <div class="second-part">

        <img class="image-1"  src="@/assets/successcheck.svg" alt="withdraw-icon"/>

        <p class="text-3">Your Certificate is Valid Till August 2026.</p>

        </div>

      </div>

    </dialog>
  </div>
</template>

<script>

export default {
  name: "FundWalletModal2",
  emits: ['close', 'open'],
  data() {
    return {
      contacts: [],
      accountNumber: '',
      bankName: '',
      bitcoinAddress: '',
      ethereumAddress: '',
      routingNumber: '',
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

    // Method to close the modal when the backdrop is clicked
    closeOnBackdropClick(event) {
      // If the click is on the backdrop (and not inside the modal content), close the modal
      if (event.target.classList.contains('backdrop')) {
        this.close();
      }
    },

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
  background-color: rgba(0, 0, 0, 0.85);
}


dialog {
  position: fixed;
  top: 5vh;
  width: 100%;
  height: 100%;

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
  width: 100%;
  height: 100%;
  margin: auto;
  /*height: auto;
  padding: 24px;

  /*border-radius: 5px;
  background-color: #0f171c;
  border: 0.5px solid #3C4A57FF;
  box-shadow: 0 0 34px 0 rgba(3, 28, 67, 0.13);*/
}

.image-1{
  display: block;
  margin-right: auto;
  margin-left: auto;
}

.first-part{
  display: flex;
  justify-content: space-between;
}

.second-part{
  margin-top: 14%;
}

.bx-x{
  font-size: 25px;
  padding-top: 2px;
  color: #ffffff;
}

.text-1{
  font-weight: 600;
  font-size: 18px;
  line-height: 28px;
  color: #0f171c;
  padding-top: 2.5%;
  padding-bottom: 1%;
}

.text-2{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #ffffff;
  padding-top: 1%;
  padding-bottom: 2%;
}

.text-3{
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #ffffff;
  padding-top: 1.5%;
  padding-bottom: 1.5%;
  text-align: center;
}

.text-4{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #ffffff;
  padding-top: 1.5%;
  padding-bottom: 1.5%;
}

.text-5{
  font-weight: 400;
  font-size: 15px;
  line-height: 24px;
  color: #ffffff;
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
  /*display: block;*/
  /*margin-left: auto;*/
  /*margin-right: auto;*/
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
    height: 610px;
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