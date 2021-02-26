<template>
  <div>
    <nav-bar />
    <home />
    <about />
    <skills />
    <work />
    <testimonials />
    <contact />
  </div>
</template>

<script>
import NavBar from "@/components/NavBar";
import Home from "@/components/Home";
import About from "@/components/About";
import Skills from "@/components/Skills";
import Work from "@/components/Work";
import Testimonials from "@/components/Testimonials";
import Contact from "@/components/Contact";

export default {
  name: "Main",
  components: {
    NavBar,
    Home,
    About,
    Skills,
    Work,
    Testimonials,
    Contact
  }
};
</script>
