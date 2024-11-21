<template>
    <section id="contacts-1" class="pb-50 inner-page-hero contacts-section division">
        <div class="container">
            <!-- SECTION TITLE -->
            <div class="row justify-content-center">
                <div class="col-md-10 col-lg-9">
                    <div class="section-title text-center mb-80">
                        <!-- Title -->
                        <h2 class="s-52 w-700">Questions? Let's Talk</h2>
                        <!-- Text -->
                        <p class="p-lg">
                            Want to know more about Upplinko, get a quote, or speak with an expert? Let us know what
                            you are looking for, and we’ll get back to you right away.
                        </p>
                    </div>
                </div>
            </div>
            <!-- CONTACT FORM -->
            <div class="row justify-content-center">
                <div class="col-md-11 col-lg-10 col-xl-8">
                    <div class="form-holder">
                        <form name="contactform" class="row contact-form" @submit.prevent="submitForm">
                            <!-- Form Select -->
                            <div class="col-md-12 input-subject">
                                <p class="p-lg">This question is about:</p>
                                <span>Choose a topic, so we know who to send your request to:</span>
                                <select class="form-select subject" aria-label="Default select example" v-model="formData.topic">
                                    <option selected disabled value="">This question is about...</option>
                                    <option>Registering/Authorising</option>
                                    <option>Need a Website</option>
                                    <option>Media Marketing</option>
                                    <option>Automation Services</option>
                                    <option>Other</option>
                                </select>
                            </div>
                            <!-- Name Field -->
                            <div class="col-md-12">
                                <p class="p-lg">Your Name:</p>
                                <span>Please enter your real name:</span>
                                <input
                                    type="text"
                                    class="form-control name"
                                    placeholder="Your Name*"
                                    v-model="formData.name"
                                    required
                                />
                            </div>
                            <!-- WhatsApp Phone Number with Country Code -->
                            <div class="col-md-12 d-flex align-items-center">
                                <div class="me-3">
                                    <p class="p-lg">Country Code:</p>
                                    <select v-model="formData.countryCode" class="form-select">
                                        <option value="+1">+1 (USA)</option>
                                        <option value="+44">+44 (UK)</option>
                                        <option value="+61">+61 (Australia)</option>
                                        <option value="+64">+64 (New Zealand)</option>
                                        <option value="+353">+353 (Ireland)</option>
                                        <option value="+1">+1 (Canada)</option>
                                        <option value="+27">+27 (South Africa)</option>
                                        <option value="+356">+356 (Malta)</option>
                                        <option value="+49">+49 (Germany)</option>
                                        <option value="+33">+33 (France)</option>
                                        <option value="+31">+31 (Netherlands)</option>
                                        <option value="+41">+41 (Switzerland)</option>
                                        <option value="+47">+47 (Norway)</option>
                                        <option value="+46">+46 (Sweden)</option>
                                        <option value="+358">+358 (Finland)</option>
                                        <option value="+39">+39 (Italy)</option>
                                        <option value="+34">+34 (Spain)</option>
                                        <option value="+81">+81 (Japan)</option>
                                        <option value="+82">+82 (South Korea)</option>
                                        <option value="+65">+65 (Singapore)</option>
                                        <option value="+852">+852 (Hong Kong)</option>
                                        <option value="+376">+376 (Andorra)</option>
                                        <option value="+48">+48 (Poland)</option>
                                        <option value="+43">+43 (Austria)</option>
                                        <option value="+32">+32 (Belgium)</option>
                                        <option value="+90">+90 (Turkey)</option>
                                        <option value="+30">+30 (Greece)</option>
                                        <option value="+420">+420 (Czech Republic)</option>
                                        <option value="+421">+421 (Slovakia)</option>
                                    </select>
                                </div>
                                <div class="flex-grow-1">
                                    <p class="p-lg">WhatsApp Phone Number:</p>
                                    <input
                                        type="text"
                                        class="form-control whatsapp"
                                        placeholder="WhatsApp Phone Number*"
                                        v-model="formData.whatsapp"
                                        required
                                    />
                                </div>
                            </div>
                            <!-- Email Field -->
                            <div class="col-md-12">
                                <p class="p-lg">Your Email Address:</p>
                                <span>Please carefully check your email address for accuracy</span>
                                <input
                                    type="email"
                                    class="form-control email"
                                    placeholder="Email Address*"
                                    v-model="formData.email"
                                    required
                                />
                            </div>
                            <!-- Message Field -->
                            <div class="col-md-12">
                                <p class="p-lg">Explain your question in detail:</p>
                                <span>Whatever you think we need to know to be prepared for our meeting. Be VERY precise!</span>
                                <textarea
                                    class="form-control message"
                                    rows="6"
                                    placeholder="I have a problem with..."
                                    v-model="formData.message"
                                    required
                                ></textarea>
                            </div>
                            <!-- Submit Button -->
                            <div class="col-md-12 mt-15 form-btn text-right">
                                <button type="submit" class="btn btn--theme hover--theme submit">Submit Request</button>
                            </div>
                            <!-- Privacy Policy -->
                            <div class="contact-form-notice">
                                <p class="p-sm">
                                    We are committed to your privacy. Upplinko uses the information you provide us to
                                    contact you about our relevant content, products, and services. You may unsubscribe
                                    from these communications at any time. For more information, check out our
                                    <NuxtLink to="/privacy">Privacy Policy</NuxtLink>.
                                </p>
                            </div>
                            <!-- Contact Form Message -->
                            <div v-if="loading" class="col-lg-12 contact-form-msg">
                                <span class="loading">Submitting...</span>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
            <!-- END CONTACT FORM -->
        </div>
        <!-- End container -->
    </section>
    <hr class="divider" />
</template>

<script>
export default {
    data() {
        return {
            formData: {
                topic: "",
                name: "",
                countryCode: "+1",
                whatsapp: "",
                email: "",
                message: "",
            },
            loading: false,
        };
    },
    methods: {
        async submitForm() {
            this.loading = true;
            const scriptURL = "https://script.google.com/macros/s/AKfycbxwYGC-oWOaz02mtMP4pWbOnEYu0nNTZkMtReYxDlapZzK5COCRvK7NpDUyHgXFFOyv/exec";

            try {
                const response = await fetch(scriptURL, {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json",
                    },
                    body: JSON.stringify(this.formData),
                });

                const result = await response.json();
                if (result.status === "success") {
                    alert("Thank you for your submission! We’ll get back to you soon.");
                    this.resetForm();
                } else {
                    alert("Something went wrong. Please try again later.");
                }
            } catch (error) {
                console.error("Error submitting form:", error);
                alert("There was an error submitting your request. Please try again.");
            } finally {
                this.loading = false;
            }
        },
        resetForm() {
            this.formData = {
                topic: "",
                name: "",
                countryCode: "+1",
                whatsapp: "",
                email: "",
                message: "",
            };
        },
    },
};
</script>

<style scoped>
.loading {
    color: #333;
    font-size: 14px;
}
</style>
