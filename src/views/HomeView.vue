<template>
  <div class="home">
    <home-section1/>
    <home-section2/>
    <home-section3/>
    <home-section4/>
    <home-section5/>
    <footer-home2/>
  </div>
</template>

<script>


import HomeSection1 from "@/components/Home/HomeSection1.vue";
import HomeSection2 from "@/components/Home/HomeSection2.vue";
import HomeSection3 from "@/components/Home/HomeSection3.vue";
import HomeSection4 from "@/components/Home/HomeSection4.vue";
import HomeSection5 from "@/components/Home/HomeSection5.vue";
import FooterHome2 from "@/components/BaseComponents/FooterHome2.vue";

export default {
  name: 'HomeView',
  components: {FooterHome2, HomeSection5, HomeSection4, HomeSection3, HomeSection2, HomeSection1},
}
</script>
