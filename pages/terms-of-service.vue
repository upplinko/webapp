<template>
    <div class="container py-100">
        <div class="row justify-content-center">
            <div class="col-md-10">
                <h1 class="h2-md mb-4">Terms of Service</h1>
                <div class="terms-content">
                    <p class="p-lg">Last updated: {{ currentDate }}</p>

                    <h4 class="h4-md mt-5">1. Acceptance of Terms</h4>
                    <p class="p-md">By accessing and using Upplinko's services, you agree to be bound by these Terms of Service.</p>

                    <h4 class="h4-md mt-5">2. Description of Services</h4>
                    <p class="p-md">Upplinko provides web development, digital solutions, and related services to clients.</p>

                    <h4 class="h4-md mt-5">3. User Accounts</h4>
                    <p class="p-md">You are responsible for:</p>
                    <ul class="simple-list">
                        <li>Maintaining the confidentiality of your account</li>
                        <li>All activities that occur under your account</li>
                        <li>Notifying us of any unauthorized use</li>
                    </ul>

                    <h4 class="h4-md mt-5">4. Payment Terms</h4>
                    <p class="p-md">
                        Payment terms are specified in individual project contracts. Payments are processed securely through our payment providers.
                    </p>

                    <h4 class="h4-md mt-5">5. Intellectual Property</h4>
                    <p class="p-md">
                        All intellectual property rights related to our services remain with Upplinko unless explicitly transferred through a contract.
                    </p>

                    <h4 class="h4-md mt-5">6. Limitation of Liability</h4>
                    <p class="p-md">
                        Upplinko shall not be liable for any indirect, incidental, special, consequential, or punitive damages.
                    </p>

                    <h4 class="h4-md mt-5">7. Changes to Terms</h4>
                    <p class="p-md">
                        We reserve the right to modify these terms at any time. Users will be notified of significant changes.
                    </p>

                    <h4 class="h4-md mt-5">8. Contact Information</h4>
                    <p class="p-md">For any questions regarding these terms, please contact us at:</p>
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
