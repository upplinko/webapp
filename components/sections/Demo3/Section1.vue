<template>
    <section id="hero-3" class="bg--fixed hero-section">
        <div class="container">
            <div class="row d-flex align-items-center">
                <!-- HERO TEXT -->
                <div class="col-md-6">
                    <div class="hero-3-txt color--white wow fadeInRight">
                        <!-- Title -->
                        <h2 class="s-60 w-700 hero-title">
                            Engage your Customers with our Creative Web Services
                        </h2>
                        <!-- Text -->
                        <p class="p-lg">
                            From eye-catching designs to seamless functionality, our web services are tailored to captivate, engage, and retain your audience.
                        </p>

                        <!-- HERO DIGITS -->
                        <div class="hero-digits mt-4">
                            <!-- DIGIT BLOCK #1 -->
                            <div id="hd-1-1" class="wow fadeInUp">
                                <div class="hero-digits-block">
                                    <!-- Digit -->
                                    <div class="block-digit">
                                        <h2 class="s-46 statistic-number">
                                            <span ref="digit1" class="shuffling-number"></span><span>x</span>
                                        </h2>
                                    </div>
                                    <!-- Text -->
                                    <div class="block-txt">
                                        <p class="p-sm">Increase in conversions</p>
                                    </div>
                                </div>
                            </div>
                            <!-- END DIGIT BLOCK #1 -->

                            <!-- DIGIT BLOCK #2 -->
                            <div id="hd-1-2" class="wow fadeInUp">
                                <div class="hero-digits-block">
                                    <!-- Digit -->
                                    <div class="block-digit">
                                        <h2 class="s-46 statistic-number">
                                            <span ref="digit2" class="shuffling-number"></span><span>%</span>
                                        </h2>
                                    </div>
                                    <!-- Text -->
                                    <div class="block-txt">
                                        <p class="p-sm">Growth in Sales</p>
                                    </div>
                                </div>
                            </div>
                            <!-- END DIGIT BLOCK #2 -->
                        </div>
                        <!-- END HERO DIGITS -->

                        <!-- Call-to-Action -->
                        <div class="cta-email mt-5">
                            <p class="p-md">Stay updated with our latest offers and services. Enter your email below:</p>
                            <form id="email-form" action="/subscribe" method="POST" class="d-flex gap-3">
                                <input 
                                    type="email" 
                                    name="email" 
                                    placeholder="Enter your email" 
                                    required 
                                    class="form-control email-input"
                                />
                                <button 
                                    type="submit" 
                                    class="btn btn-primary btn-submit shadow-effect"
                                >
                                    Subscribe
                                </button>
                            </form>
                        </div>
                    </div>
                </div>
                <!-- END HERO TEXT -->

                <!-- HERO IMAGE -->
                <div class="col-md-6">
                    <div class="hero-3-img wow fadeInLeft">
                        <img 
                            class="img-fluid" 
                            src="/assets/images/tablet-01.png" 
                            alt="hero-image" 
                        />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    mounted() {
        // Shuffling animation for numbers
        this.animateNumber(this.$refs.digit1, 3, 2000); // Animate to "3"
        this.animateNumber(this.$refs.digit2, 29, 2500); // Animate to "29"
    },
    methods: {
        animateNumber(element, targetNumber, duration) {
            let start = 0; // Start from 0
            let increment = targetNumber / (duration / 50); // Adjust increment for 50ms intervals

            const interval = setInterval(() => {
                start += increment;
                if (start >= targetNumber) {
                    start = targetNumber; // Ensure it stops at target
                    clearInterval(interval);
                }
                element.textContent = Math.floor(start); // Update displayed number
            }, 50); // Update every 50ms
        }
    }
};
</script>

<style scoped>
/* Hero Title Font Size Adjustment */
.hero-title {
    font-size: 48px; /* Smaller size for improved readability */
    line-height: 1.2; /* Adjust line height for better spacing */
}

/* Email Input Animation */
.email-input {
    transition: all 0.3s ease; /* Smooth transition */
}

.email-input:focus {
    border-color: #007bff; /* Highlight border color on focus */
    box-shadow: 0 0 8px rgba(0, 123, 255, 0.6); /* Blue glow effect */
    outline: none; /* Remove default outline */
}

/* Button Shadow and Animation */
.btn-submit {
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.5); /* Initial shadow */
    transition: all 0.3s ease; /* Smooth transition */
}

.btn-submit:hover {
    box-shadow: 0px 6px 8px rgba(0, 0, 0, 0.3); /* Enhanced shadow on hover */
    transform: translateY(-2px); /* Slight lift effect */
}

.btn-submit:active {
    transform: translateY(1px); /* Simulates button press */
    box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.3); /* Reduced shadow on press */
}

/* Number Shuffling Effect */
.shuffling-number {
    display: inline-block;
    font-weight: bold;
    color: #ffffff;
    transition: transform 0.3s ease; /* Optional styling */
}
</style>
