<template>
    <div class="container py-100">
        <div class="row justify-content-center">
            <div class="col-md-10">
                <h1 class="h2-md mb-4">Privacy Policy</h1>
                <div class="privacy-content">
                    <p class="p-lg">Last updated: {{ currentDate }}</p>

                    <h4 class="h4-md mt-5">1. Information We Collect</h4>
                    <p class="p-md">We collect information that you provide directly to us, including:</p>
                    <ul class="simple-list">
                        <li>Name and contact information</li>
                        <li>Account credentials</li>
                        <li>Payment information</li>
                        <li>Project-related information</li>
                    </ul>

                    <h4 class="h4-md mt-5">2. How We Use Your Information</h4>
                    <p class="p-md">We use the information we collect to:</p>
                    <ul class="simple-list">
                        <li>Provide and maintain our services</li>
                        <li>Process your payments</li>
                        <li>Send you important updates</li>
                        <li>Improve our services</li>
                    </ul>

                    <h4 class="h4-md mt-5">3. Information Sharing</h4>
                    <p class="p-md">We do not sell your personal information. We may share your information with:</p>
                    <ul class="simple-list">
                        <li>Service providers (payment processors, hosting services)</li>
                        <li>Legal authorities when required by law</li>
                    </ul>

                    <h4 class="h4-md mt-5">4. Data Security</h4>
                    <p class="p-md">We implement appropriate security measures to protect your personal information.</p>

                    <h4 class="h4-md mt-5">5. Contact Us</h4>
                    <p class="p-md">If you have any questions about this Privacy Policy, please contact us at:</p>
                    <p class="p-md">Email: support@upplinko.com</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentDate: new Date().toLocaleDateString('en-US', {
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            })
        }
    }
}
</script>
