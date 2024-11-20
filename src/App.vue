<template>
  <div>
    <TopNav :isScrolled="isScrolled" />
    <SwipperSlider />
    <h1>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Unde harum itaque architecto autem beatae ab culpa, ex
      blanditiis aliquam veritatis in vel dicta sapiente quisquam voluptas reprehenderit molestiae nobis dolor.
      Reprehenderit accusantium at sit repellendus aspernatur consequuntur esse pariatur temporibus cupiditate,
      nesciunt, beatae magnam odio porro eos ipsa tenetur? Omnis mollitia ipsam quia voluptas? Corporis, atque. Nobis
      consectetur omnis quos illo autem commodi voluptatem nihil nostrum dicta eaque voluptatibus, reprehenderit fuga
      nemo incidunt. Dolores, optio! Molestiae, minus qui cumque aliquam nisi obcaecati repudiandae similique harum,
      impedit quidem fugiat recusandae eos quis. Magnam laboriosam hic natus ipsum! Alias officiis quo consequatur!</h1>
  </div>
</template>

<script>
import SwipperSlider from './components/SwipperSlider.vue';
import TopNav from './components/TopNav.vue';

export default {
  components: {
    SwipperSlider, TopNav
  },
  data() {
    return {
      isScrolled: false,
    };
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50;
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },

}
</script>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

h1,
h2 {
  margin: 0;
}
</style>