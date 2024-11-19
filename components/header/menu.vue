<template>
    <div id="main-menu" class="wsmainfull menu clearfix">
        <div class="wsmainwp clearfix">
            <!-- HEADER BLACK LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-black"><img src="/assets/images/logo-blue.png" alt="logo" /></NuxtLink>
            </div>
            <!-- HEADER WHITE LOGO -->
            <div class="desktoplogo">
                <NuxtLink to="/" class="logo-white"><img src="/assets/images/logo-white.png" alt="logo" /></NuxtLink>
            </div>
            <!-- MAIN MENU -->
            <nav class="wsmenu clearfix">
                <ul class="wsmenu-list nav-theme">
                    <!-- SIMPLE NAVIGATION LINK FOR HOME WITHOUT DROPDOWN ICON AND MEGA MENU -->
                    <li class="nl-simple" aria-haspopup="true">
                        <NuxtLink to="/" class="h-link">Home</NuxtLink>
                    </li>
                    
                    <!-- SIMPLE NAVIGATION LINK -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/about" class="h-link">About Us</NuxtLink></li>
                    
                    <!-- MEGAMENU FOR SERVICES WITH FOUR COLUMNS -->
                    <li aria-haspopup="true" class="mg_link" :class="{ open: isOpen[1] }">
                        <span class="wsmenu-click" @click="toggle(1)"><i class="wsmenu-arrow"></i></span>
                        <NuxtLink to="#" class="h-link">Services <span class="wsarrow"></span></NuxtLink>
                        <div class="wsmegamenu w-75 clearfix">
                            <div class="container">
                                <div class="row">
                                    <!-- Column 1: Web Design & Development -->
                                    <ul class="col-md-12 col-lg-3 link-list">
                                        <li><NuxtLink to="/demo-17">Websites/Web Apps</NuxtLink></li>
                                        <li><NuxtLink to="/demo-11">Landing Pages</NuxtLink></li>
                                        <li><NuxtLink to="/demo-17">E-commerce Stores</NuxtLink></li>
                                        <li><NuxtLink to="/demo-17">Custom Stack</NuxtLink></li>
                                        <li><NuxtLink to="/demo-5">CMS Solutions</NuxtLink></li>
                                    </ul>
                                    
                                    <!-- Column 2: Design & UX/UI -->
                                    <ul class="col-md-12 col-lg-3 link-list">
                                        <li><NuxtLink to="/demo-12">UX/UI Design</NuxtLink></li>
                                        <li><NuxtLink to="/demo-11">Responsive Web Design</NuxtLink></li>
                                        <li><NuxtLink to="demo-25">Brand Identity</NuxtLink></li>
                                        <li><NuxtLink to="/demo-11">Prototyping & Wireframing</NuxtLink></li>
                                        <li><NuxtLink to="/demo-12">Web Animations</NuxtLink></li>
                                    </ul>
                                    
                                    <!-- Column 3: Digital Marketing -->
                                    <ul class="col-md-12 col-lg-3 link-list">
                                        <li><NuxtLink to="/demo-13">SEO</NuxtLink></li>
                                        <li><NuxtLink to="/demo-1">Content Marketing</NuxtLink></li>
                                        <li><NuxtLink to="/demo-20">PPC Advertising</NuxtLink></li>
                                        <li><NuxtLink to="/demo-23">Social Media Marketing</NuxtLink></li>
                                        <li><NuxtLink to="/demo-22">Email Marketing</NuxtLink></li>
                                    </ul>
                                    
                                    <!-- Column 4: Strategy & Automation -->
                                    <ul class="col-md-12 col-lg-3 link-list">
                                        <li><NuxtLink to="/demo-24">Automationn</NuxtLink></li>
                                        <li><NuxtLink to="/demo-25">Brand Strategy</NuxtLink></li>
                                        <li><NuxtLink to="/demo-26">ORM</NuxtLink></li>
                                        <li><NuxtLink to="/demo-21">Analytics & Insights</NuxtLink></li>
                                        <li><NuxtLink to="/demo-27">Consulting</NuxtLink></li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </li>

                    <!-- SIMPLE NAVIGATION LINK -->
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/pricing-1" class="h-link">Pricing</NuxtLink></li>
                    <li class="nl-simple" aria-haspopup="true"><NuxtLink to="/contacts" class="h-link">Contact</NuxtLink></li>
                    
                    <!-- SIGN IN LINK -->
                    <li class="nl-simple reg-fst-link mobile-last-link" aria-haspopup="true">
                        <NuxtLink to="/login-2" class="h-link">Sign in</NuxtLink>
                    </li>
                    <!-- SIGN UP BUTTON -->
                    <li class="nl-simple" aria-haspopup="true">
                        <NuxtLink to="/signup-2" class="btn r-04 btn--theme hover--tra-white last-link">Sign up</NuxtLink>
                    </li>
                </ul>
            </nav>
            <!-- END MAIN MENU -->
        </div>
    </div>
</template>

<script>
import { reactive } from 'vue';
export default {
    setup() {
        const state = reactive({
            isOpen: [false, false]
        });
        const toggle = (index) => {
            state.isOpen[index] = !state.isOpen[index];
        };
        return {
            toggle,
            isOpen: state.isOpen
        };
    },
    mounted() {
        window.addEventListener("scroll", this.handleScroll);
    },
    beforeUnmount() {
        window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll() {
            const menu = document.getElementById("main-menu");
            const header = document.getElementById("header");
            if (window.pageYOffset > 100) {
                menu.classList.add("scroll");
                header.classList.add("scroll");
            } else {
                menu.classList.remove("scroll");
                header.classList.remove("scroll");
            }
        }
    }
};
</script>

<style scoped>
#main-menu > div .h-link {
    font-weight: 550 !important;
}

#main-menu > div .h-link {
    margin-left: 35px !important; /* Adjust as needed */
}

</style>
