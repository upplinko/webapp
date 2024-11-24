<template>
    <section id="hero-7" class="gr--perl hero-section">
        <div class="hero-overlay">
            <div class="container">
                <div class="row d-flex align-items-center">
                    <!-- HERO TEXT -->
                    <div class="col-md-6">
                        <div class="hero-7-txt wow fadeInRight">
                            <!-- Title -->
                            <h2 class="s-54 w-700">Empowering your business with innovative digital solutions</h2>
                            <!-- Text -->
                            <p class="p-lg">At Upplinko, we specialize in crafting creative web services and strategies that drive results and elevate your brand.</p>
                            <!-- HERO QUICK FORM -->
                            <form
                                id="ctaForm"
                                name="quickform"
                                class="quick-form form-shadow form-half mt-35"
                                @submit.prevent="submitForm"
                            >
                                <!-- Caption -->
                                <p class="p-sm text-muted mb-3">Results That Matter, Starting Today! 35% Off for First-Time Clients.</p>
                                <!-- Form Inputs -->
                                <div class="input-group">
                                    <input
                                        v-model="formData.email"
                                        type="email"
                                        name="email"
                                        class="form-control email r-06"
                                        placeholder="Your email address"
                                        autocomplete="off"
                                        required
                                    />
                                    <span class="input-group-btn form-btn">
                                        <button type="submit" class="btn r-06 btn--theme hover--theme submit">Let's Go</button>
                                    </span>
                                </div>
                                <!-- Success Message -->
                                <div v-if="successMessage" class="alert alert-success mt-3" role="alert">
                                    {{ successMessage }}
                                </div>
                                <!-- Error Message -->
                                <div v-if="errorMessage" class="alert alert-danger mt-3" role="alert">
                                    {{ errorMessage }}
                                </div>
                            </form>
                            <!-- END HERO QUICK FORM -->
                            <!-- Text -->
                            <p class="p-sm btn-txt ico-15"><span class="flaticon-check"></span> No credit card needed, free 14-day trial</p>
                        </div>
                    </div>
                    <!-- END HERO TEXT -->
                    <!-- HERO IMAGE -->
                    <div class="col-md-6">
                        <div class="hero-7-img text-center wow fadeInLeft">
                            <img class="img-fluid" src="/assets/images/img-06.png" alt="hero-image" />
                        </div>
                    </div>
                </div>
                <!-- End row -->
            </div>
            <!-- End container -->
        </div>
        <!-- End hero-overlay -->
    </section>
</template>

<script>
export default {
    data() {
        return {
            formData: {
                email: ""
            },
            successMessage: "",
            errorMessage: ""
        };
    },
    methods: {
        async submitForm() {
            const googleScriptUrl = "https://script.google.com/macros/s/AKfycbyqqqpZKJa6D70a9YXorQo8PDGGdgz9K8hwhUlEaqQJZwu6ewhDRRVtl6iGK7DLjikqdw/exec"; // Replace with your Google Apps Script URL

            try {
                const response = await fetch(googleScriptUrl, {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify(this.formData)
                });

                const result = await response.json();

                if (result.success) {
                    this.successMessage = "Thank you! Your submission was successful.";
                    this.errorMessage = "";
                    this.formData.email = ""; // Clear the form
                } else {
                    this.errorMessage = "Something went wrong. Please try again.";
                    this.successMessage = "";
                }
            } catch (error) {
                console.error("Error:", error);
                this.errorMessage = "Failed to submit the form. Please try again later.";
                this.successMessage = "";
            }
        }
    }
};
</script>

<style scoped>
/* Add custom styles if needed */
.alert {
    font-size: 14px;
    font-weight: 500;
}
</style>
