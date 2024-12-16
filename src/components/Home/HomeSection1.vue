<template>
  <div class="alpha">
    <div class="section-1">
      <img src="@/assets/Subtractlarge-1.svg" alt="Subtractlarge" class="image"/>
      <h1 class="text-1">
        Verification Tool</h1>
    </div>

    <p class="text-2">Verifiable trust: Check the authenticity and integrity of your trading document. and protect yourself from fraud</p>
  </div>
</template>

<script>
export default {
  name: "HomeSection1"
}
</script>

<style scoped>
.section-1{
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  font-family: 'BR-Firma-Bold', sans-serif;
  margin-top: 3%;
  margin-bottom: 1%;
}

.text-1{
  margin-left: 1%;
  font-size: 35px;
}

.text-2{
  text-align: center;
  font-size: 18px;
  font-family: 'BR-Firma-Light', sans-serif;
}


@media (max-width: 990px) {

}

@media (max-width: 700px) {
  .text-2{
    text-align: left;
    width: 95%;
    font-size: 17px;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2%;
  }
}

@media (max-width: 500px) {
  .text-1{
    font-size: 32px;
    margin-top: 1%;
  }

}
</style>