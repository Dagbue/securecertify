<template>
  <div class="alpha">

    <div class="section-1">
      <p class="text-1">Test out our verification tool</p>
      <p class="text-2">Try it for yourself: verify a Trading document</p>
    </div>

    <div class="section-2">

      <div class="section-2-alpha">

        <div class="section-2-inner">
          <img src="@/assets/One.svg" alt="Subtractlarge" class="image"/>
          <p class="text-3">Upload your trading document</p>
<!--          <p class="text-4">Download one of our demo documents</p>-->
        </div>

        <div class="section-2-inner">
          <img src="@/assets/Two.svg" alt="Subtractlarge" class="image"/>
          <p class="text-3">Verify with our verification tool</p>
          <p class="text-4">Drag & drop each trading document into the tool or click on the tool to open your file browser
            and select it from there.</p>
        </div>

        <div class="section-2-inner">
          <img src="@/assets/Three.svg" alt="Subtractlarge" class="image"/>
          <p class="text-3">Try to manipulate a valid document</p>
          <p class="text-4">Our powerful tool spots the change of one single pixel and everything beyond.</p>
        </div>


      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "HomeSection4"
}
</script>

<style scoped>

.alpha{
  padding-top: 10%;
  padding-bottom: 10%;
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
  text-align: left;
  font-size: 20px;
  margin-top: 10px;
  margin-bottom: 10px;
}

.text-4{
  font-family: 'BR-Firma-Light', sans-serif;
  line-height: 1.5;
  text-align: left;
}

.section-2-alpha{
  display: flex;
  justify-content: space-evenly;
  gap: 20px;
  margin-top: 5%;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.section-2-inner{
  width: 33%;
}


@media (max-width: 990px) {

}

@media (max-width: 700px) {
  .section-2-alpha{
    display: block;
  }
  .image{
    display: block;
  }
  .section-2-inner{
    width: 100%;
    margin-bottom: 3%;
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