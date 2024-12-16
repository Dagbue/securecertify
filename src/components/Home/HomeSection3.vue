<template>
  <div class="alpha">

    <div class="section-1">
      <p class="text-1">How to use the verification tool</p>
      <p class="text-2">Instantly verify the authenticity of your Trading document</p>
    </div>

    <div class="section-2">

      <div class="section-2-alpha">

        <div class="section-2-inner">
          <p class="text-3">Insert Trading document in the tool  without <br/> uploading them</p>
          <img src="@/assets/image-1.svg" alt="Subtractlarge" class="image"/>
        </div>

        <div class="section-2-inner">
          <p class="text-3">Authentic status example</p>
          <img src="@/assets/image-2.png" alt="Subtractlarge" class="image"/>
        </div>

        <div class="section-2-inner">
          <p class="text-3">Unverified status example</p>
          <img src="@/assets/image-3.png" alt="Subtractlarge" class="image"/>
        </div>


      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "HomeSection3"
}
</script>

<style scoped>

.alpha{
  background-color: #f7f9fc;
  padding-top: 5%;
  padding-bottom: 3%;
  margin-top: 8%;
}
.section-1{
  margin-left: 10%;
}
.text-1{
  font-family: 'BR-Firma-Bold', sans-serif;
  font-size: 18px;
  color: #0669f2 !important;
  padding-bottom: 1%;
}

.text-2{
  font-size: 23px;
  font-family: 'BR-Firma-Light', sans-serif;
}

.text-3{
  font-family: 'BR-Firma-Bold', sans-serif;
  text-align: center;
  font-size: 19px;

}

.section-2-alpha{
  display: flex;
  justify-content: space-evenly;
  gap: 20px;
  margin-top: 5%;
}

@media (max-width: 990px) {

}

@media (max-width: 700px) {
  .section-2-alpha{
    display: block;
  }
  .image{
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
  .text-2{
    font-size: 21px;
  }
  .text-1{
    font-size: 19px;
  }
  .section-1{
    margin-left: 5%;
  }
}

@media (max-width: 500px) {

}
</style>