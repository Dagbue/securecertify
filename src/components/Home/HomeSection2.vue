<template>
  <div>
    <label for="files" class="drop-container" @dragover.prevent="handleDragOver" @dragenter="handleDragEnter" @dragleave="handleDragLeave" @drop.prevent="handleDrop">
      <span class="drop-title">Drop files here</span>
      <input type="file" id="files" ref="fileInput" @change="handleFileChange" required>
<!--      <div class="second-part">-->

<!--        <img class="image-1"  src="@/assets/successcheck.svg" alt="withdraw-icon"/>-->

<!--        <p class="text-image">Your Certificate is Valid Till August 2026.</p>-->

<!--      </div>-->

    </label>
    <div class="seprate" v-if="loading === true">
      <span class="loader"></span>
      <p class="loader-text" style="padding-left: 5px;">Uploading</p>

    </div>
    <div class="seprate" v-if="loading2 === true">
      <span class="loader"></span>
      <p class="loader-text" style="padding-left: 5px;">Verifying</p>

    </div>
    <button @click="handleButtonClick" v-if="button1" class="auth">Verify Now</button>
    <div class="seprate-2" v-if="loading3 === true">
      <span class="loader-3"></span>
      <p class="loader-text" style="padding-left: 5px;">Verifying ...</p>

    </div>
    <div class="text-1">
      <span>Powered by</span>
      <img src="@/assets/logo2.png" class="last-img"/>
      <span>SecureCertify</span>
    </div>
    <fund-wallet-modal @close="hideDialog" @open="showDialog2" v-if="dialogIsVisible"  />
    <fund-wallet-modal2 @close="hideDialog2"   v-if="dialogIsVisible2" />
  </div>
</template>

<script>
import FundWalletModal from "@/components/BaseComponents/modal/FundWalletModal.vue";
import Toastify from 'toastify-js'
import 'toastify-js/src/toastify.css'
import FundWalletModal2 from "@/components/BaseComponents/modal/FundWalletModal2.vue";

export default {
  name: 'HomeSection2',
  components: {FundWalletModal2, FundWalletModal},
  data() {
    return {
      inputValue: '',
      loading: false,
      loading2: false,
      loading3: false,
      dialogIsVisible: false,
      dialogIsVisible2: false,
      selectValue: "",
      button1: false,
    };
  },
  methods: {
    handleDragOver(event) {
      event.preventDefault();
    },
    handleDragEnter() {
      const container = this.$refs.dropContainer;
      container.classList.add('drag-active');
    },
    handleDragLeave() {
      const container = this.$refs.dropContainer;
      container.classList.remove('drag-active');
    },
    handleDrop(event) {
      const container = this.$refs.dropContainer;
      container.classList.remove('drag-active');
      const files = event.dataTransfer.files;
      this.$refs.fileInput.files = files;
      this.handleFileChange(); // Handle file process or emit event here
    },
    // handleFileChange() {
    //   // You might want to emit an event or process the file
    //   const files = this.$refs.fileInput.files;
    //   console.log(files);
    //   // Emit an event if you want parent components to listen to the file changes
    //   this.$emit('files-changed', files);
    // }
    handleFileChange() {
      if (this.$refs.fileInput.files.length > 0) {
        this.startLoading();
      }
    },

    startLoading() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
        this.showToast();
        this.startSecondaryLoading();
      }, 20000);
    },
    startSecondaryLoading() {
      this.loading2 = true;
      setTimeout(() => {
        this.loading2 = false;
        this.showButton();
      }, 20000);
    },
    showButton() {
      this.button1 = true;
    },
    handleButtonClick() {
      this.loading3 = true;
      setTimeout(() => {
        this.loading3 = false;
        this.button1 = false;
        this.showToast2();
        this.dialogIsVisible = true; // Show the loader
      }, 20000); // 20 seconds
    },
    hideDialog() {
      this.dialogIsVisible = false;
    },
    showDialog() {
      this.dialogIsVisible = true; // Show the loader
    },
    // hideDialog2() {
    //   this.dialogIsVisible2 = false;
    // },
    hideDialog2() {
      this.dialogIsVisible2 = false;
      if (this.$refs.fileInput) {
        this.$refs.fileInput.value = '';
      }
    },
    showDialog2() {
      this.dialogIsVisible2 = true; // Show the loader
    },
    showToast() {
      Toastify({
        text: "Document Uploaded Successfully",
        duration: 4000,
        close: true,
        gravity: "top", // `top` or `bottom`
        position: "center", // `left`, `center` or `right`
        backgroundColor: "#39a539",
        stopOnFocus: true, // Prevents dismissing of toast on hover
        onClick: function(){} // Callback after click
      }).showToast();
    },
    showToast2() {
      Toastify({
        text: "Document Verified Successfully",
        duration: 4000,
        close: true,
        gravity: "top", // `top` or `bottom`
        position: "center", // `left`, `center` or `right`
        backgroundColor: "#39a539",
        stopOnFocus: true, // Prevents dismissing of toast on hover
        onClick: function(){} // Callback after click
      }).showToast();
    },
    showToast3() {
      Toastify({
        text: "Document Verified Successfully",
        duration: 4000,
        close: true,
        gravity: "top", // `top` or `bottom`
        position: "center", // `left`, `center` or `right`
        backgroundColor: "#39a539",
        stopOnFocus: true, // Prevents dismissing of toast on hover
        onClick: function(){} // Callback after click
      }).showToast();
    },
  }
}
</script>

<style scoped>
.drop-container {
  position: relative;
  display: flex;
  gap: 10px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 170px;
  padding: 20px;
  border-radius: 5px;
  border: 1px dashed #0669f2;
  color: #f7f9fc;
  cursor: pointer;
  transition: background .2s ease-in-out, border .2s ease-in-out;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
  margin-top: 5%;
  background-color: #f7f9fc;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}

.drop-container:hover,
.drop-container.drag-active {
  background: #f7f9fc;
}

.drop-container:hover .drop-title,
.drop-container.drag-active .drop-title {
  color: #222;
}

.drop-title {
  color: #444;
  font-size: 17px;
  text-align: center;
  transition: color .2s ease-in-out;
  font-family: 'BR-Firma-Light', sans-serif;
  letter-spacing: -0.5px;
}

input[type=file] {
  width: 350px;
  max-width: 100%;
  color: #444;
  padding: 5px;
  background-color: #f7f9fc;
  border-radius: 5px;
  border: 1px dashed #0669f2;
}

input[type=file]::file-selector-button {
  margin-right: 20px;
  border: none;
  background: #084cdf;
  padding: 10px 20px;
  border-radius: 10px;
  color: #fff;
  cursor: pointer;
  transition: background .2s ease-in-out;
}

input[type=file]::file-selector-button:hover {
  background: #0d45a5;
}

.text-1{
  border: 1px solid #ebedf1;
  margin-top: 2%;
  padding-top: 7px;
  padding-bottom: 7px;
  border-radius: 5px;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  font-family: 'BR-Firma-Light', sans-serif;
  letter-spacing: -0.5px;
  font-size: 14px;
  align-items: center;
  align-content: center;
  display: flex;
  align-items: center;
  align-content: center;
  justify-content: center;
  width: 20%;
  margin-right: auto;
  margin-left: auto;
}

.loader {
  width: 82%;
  height: 4.8px;
  display: inline-block;
  position: relative;
  background: rgba(255, 255, 255, 0.15);
  overflow: hidden;
}
.loader::after {
  content: '';
  width: 192px;
  height: 4.8px;
  background: #0669f2;
  position: absolute;
  top: 0;
  left: 0;
  box-sizing: border-box;
  animation: animloader 2s linear infinite;
}

@keyframes animloader {
  0% {
    left: 0;
    transform: translateX(-100%);
  }
  100% {
    left: 100%;
    transform: translateX(0%);
  }
}


.loader2 {
  width: 28px;
  height: 28px;
  border: 5px solid #0669f2;
  border-bottom-color: transparent;
  border-radius: 50%;
  display: inline-block;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
  margin-bottom: 5px;
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
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.seprate-2{
  display: block;
  margin-top: 20px;
  margin-bottom: 10px;
  text-align: center;
}

.auth{
  background: #0669f2;
  border: 1px solid #0669f2;
  color: #FFFFFF;
  padding: 0.9em 90px;
  border-radius: 5px;
  position: relative;
  display: block;
  margin: 0;
  text-decoration: none;
  -webkit-transition: all 0.1s ease;
  transition: all 0.25s ease;
  margin-left: auto;
  margin-right: auto;
  margin-top: 2%;
}
.auth:hover{
  background: #2474e1;
  border: 1px solid #2474e1;
  color: #FFFFFF;
}


.loader-3 {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  display: block;
  margin:15px auto;
  position: relative;
  background: #FFF;
  box-shadow: -24px 0 #FFF, 24px 0 #FFF;
  box-sizing: border-box;
  animation: shadowPulse 2s linear infinite;
}

@keyframes shadowPulse {
  33% {
    background: #FFF;
    box-shadow: -24px 0 #0669f2, 24px 0 #FFF;
  }
  66% {
    background: #0669f2;
    box-shadow: -24px 0 #FFF, 24px 0 #FFF;
  }
  100% {
    background: #FFF;
    box-shadow: -24px 0 #FFF, 24px 0 #0669f2;
  }
}

.last-img{
  width: 5%;
  margin-left: 2.5px;
  margin-right: 2.5px;
}

@media (max-width: 990px) {

}

@media (max-width: 700px) {
  .text-1{
    width: 43%;
    font-size: 12px;
  }
}

@media (max-width: 500px) {
  .last-img{
    width: 9%;
  }

}
</style>
