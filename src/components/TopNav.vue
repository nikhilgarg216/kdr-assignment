<template>
  <div>
    <!-- First Navbar -->
    <nav class="navbar navbar-expand-lg first-nav" :class="{ hidden: isScrolled && !isCollapseOpen }">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="https://www.kdrsoft.com/logo-images/52-kdrsoft-logo.webp" alt="Logo" width="200"
            class="d-inline-block align-text-top" />
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar"
          aria-controls="offcanvasNavbar">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="offcanvas offcanvas-start" style="width: 300px;" tabindex="-1" id="offcanvasNavbar"
            aria-labelledby="offcanvasNavbarLabel">
            <div class="d-lg-none offcanvas-header border-bottom  d-flex justify-content-between align-items-center p-2">
              <img src="https://www.kdrsoft.com/logo-images/52-kdrsoft-logo.webp" alt="Logo" width="90"  />
              <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
            </div>
          <ul class="navbar-nav fw-bold fs-5 ms-2">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">About Us</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Pricing</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">CSR</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Services</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Our Capabilities</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Blog</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">FAQ's</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Careers</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Contact Us</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Second Navbar -->
     
    <nav class=" navbar navbar-expand-lg second-nav" :class="{ visible: isScrolled && !isCollapseOpen }">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="https://www.kdrsoft.com/logo-images/52-kdrsoft-logo.webp" alt="Logo" width="200"
            class="d-inline-block align-text-top" />
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbarr"
          aria-controls="offcanvasNavbarr">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="offcanvas offcanvas-start" style="width: 300px;" tabindex="-1" id="offcanvasNavbarr"
            aria-labelledby="offcanvasNavbarLabel">
            <div class="d-lg-none offcanvas-header border-bottom  d-flex justify-content-between align-items-center p-2">
              <img src="https://www.kdrsoft.com/logo-images/52-kdrsoft-logo.webp" alt="Logo" width="90"  />
              <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
            </div>
          <ul class="navbar-nav fw-bold fs-5 ms-2">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">About Us</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Pricing</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">CSR</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Services</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Our Capabilities</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Blog</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">FAQ's</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Careers</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Contact Us</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isScrolled: false,  
      isCollapseOpen: false,   
    };
  },
  methods: {
    handleScroll() { 
      if (!this.isCollapseOpen) {
        this.isScrolled = window.scrollY > 50;   
      }
    },
    toggleCollapse() {
      this.isCollapseOpen = !this.isCollapseOpen;  
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);   
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>
<style scoped>
.first-nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  background-color: #eee;
  transition: transform 0.6s ease, opacity 0.6s ease;
}

.first-nav.hidden {
  transform: translateY(-100%);
  opacity: 0;
}

.second-nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 999;
  background-color: rgba(255, 255, 255, 0.766);
  color: white;
  opacity: 0;
  transform: translateY(-100%);
  transition: transform 1.5s ease, opacity 1.5s ease;
}

.second-nav.visible {
  transform: translateY(0);
  opacity: 1;
}
.navbar-toggler {
  padding: 9px;
  font-size: 12px;
}
.offcanvas { 
  --bs-offcanvas-transition: transform 1s ease-in-out !important;
  --bs-offcanvas-title-line-height: 1.5;
  height: 100vh;
}
</style>
