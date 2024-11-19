<template>
    <section id="pricing" class="pb-40 inner-page-hero pricing-section">
        <div class="container">
            <!-- SECTION TITLE -->
            <div class="row justify-content-center">
                <div class="col-md-10 col-lg-8">
                    <div class="section-title mb-70 text-center">
                        <h2 class="s-52 w-700">Our Pricing Plans</h2>
                        <p class="color--grey">Choose a plan that suits your business needs.</p>
                    </div>
                </div>
            </div>
            <!-- PRICING TABLES -->
            <div class="pricing-wrapper">
                <!-- DIGITAL MARKETING -->
                <div class="pricing-category mb-60">
                    <h3 class="s-36 text-center mb-30">Digital Marketing</h3>
                    <div class="toggle-btn ext-toggle-btn toggle-btn-md text-center">
                        <span class="toggler-txt">Billed monthly</span>
                        <label class="switch-wrap">
                            <input type="checkbox" @change="toggleDMPrices" />
                            <span class="switcher bg--grey switcher--theme"></span>
                        </label>
                        <span class="toggler-txt">Billed quarterly</span>
                    </div>
                    <div class="row row-cols-1 row-cols-md-3 mt-30">
                        <div class="col" v-for="(plan, index) in digitalMarketingPlans" :key="index">
                            <div class="p-table bg--white-100 block-shadow r-12 wow fadeInUp">
                                <h5 class="s-24">{{ plan.title }}</h5>
                                <div class="price">
                                    <sup class="color--black">$</sup>
                                    <span class="color--black">{{ plan.price }}</span>
                                    <sup class="validity color--grey">/ {{ plan.billingCycle }}</sup>
                                </div>
                                <p class="color--grey">{{ plan.description }}</p>
                                <ul class="service-list">
                                    <li v-for="(service, i) in plan.services" :key="i">{{ service }}</li>
                                </ul>
                                <a href="#" class="pt-btn btn r-04 btn--theme hover--theme">Get Started</a>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- WEBSITE DESIGN -->
                <div class="pricing-category mb-60">
                    <h3 class="s-36 text-center mb-30">Website Design & Development</h3>
                    <div class="row row-cols-1 row-cols-md-3">
                        <div class="col" v-for="(plan, index) in websiteDesignPlans" :key="index">
                            <div class="p-table bg--white-100 block-shadow r-12 wow fadeInUp">
                                <h5 class="s-24">{{ plan.title }}</h5>
                                <div class="price">
                                    <sup class="color--black">$</sup>
                                    <span class="color--black">{{ plan.price }}</span>
                                    <sup class="validity color--grey">/ one-time</sup>
                                </div>
                                <p class="color--grey">{{ plan.description }}</p>
                                <ul class="service-list">
                                    <li v-for="(service, i) in plan.services" :key="i">{{ service }}</li>
                                </ul>
                                <a href="#" class="pt-btn btn r-04 btn--theme hover--theme">Get Started</a>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- SEO SERVICES -->
                <div class="pricing-category mb-60">
                    <h3 class="s-36 text-center mb-30">SEO Services</h3>
                    <div class="toggle-btn ext-toggle-btn toggle-btn-md text-center">
                        <span class="toggler-txt">Billed monthly</span>
                        <label class="switch-wrap">
                            <input type="checkbox" @change="toggleSEOPrices" />
                            <span class="switcher bg--grey switcher--theme"></span>
                        </label>
                        <span class="toggler-txt">6-Monthly Billing</span>
                    </div>
                    <div class="row row-cols-1 row-cols-md-3 mt-30">
                        <div class="col" v-for="(plan, index) in seoPlans" :key="index">
                            <div class="p-table bg--white-100 block-shadow r-12 wow fadeInUp">
                                <h5 class="s-24">{{ plan.title }}</h5>
                                <div class="price">
                                    <sup class="color--black">$</sup>
                                    <span class="color--black">{{ plan.price }}</span>
                                    <sup class="validity color--grey">/ {{ plan.billingCycle }}</sup>
                                </div>
                                <p class="color--grey">{{ plan.description }}</p>
                                <ul class="service-list">
                                    <li v-for="(service, i) in plan.services" :key="i">{{ service }}</li>
                                </ul>
                                <a href="#" class="pt-btn btn r-04 btn--theme hover--theme">Get Started</a>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- AUTOMATION SERVICES -->
                <div class="pricing-category">
                    <h3 class="s-36 text-center mb-30">Automation Services</h3>
                    <div class="row row-cols-1 row-cols-md-3">
                        <div class="col" v-for="(plan, index) in automationPlans" :key="index">
                            <div class="p-table bg--white-100 block-shadow r-12 wow fadeInUp">
                                <h5 class="s-24">{{ plan.title }}</h5>
                                <div class="price">
                                    <sup class="color--black">$</sup>
                                    <span class="color--black">{{ plan.price }}</span>
                                    <sup class="validity color--grey">/ month</sup>
                                </div>
                                <p class="color--grey">{{ plan.description }}</p>
                                <ul class="service-list">
                                    <li v-for="(service, i) in plan.services" :key="i">{{ service }}</li>
                                </ul>
                                <a href="#" class="pt-btn btn r-04 btn--theme hover--theme">Get Started</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            isQuarterlyDM: false,
            isSixMonthlySEO: false,
            digitalMarketingPlans: [
                {
                    title: "Basic",
                    price: 999,
                    billingCycle: "mo",
                    description: "Starter package for small businesses.",
                    services: [
                        "Social media management",
                        "Monthly SEO audit",
                        "Content curation",
                        "Ad campaign setup",
                        "Performance analytics",
                        "Basic keyword research",
                        "Monthly progress report",
                        "Initial consultation",
                    ],
                },
                {
                    title: "Standard",
                    price: 1999,
                    billingCycle: "mo",
                    description: "Enhanced plan for growing businesses.",
                    services: [
                        "Everything in Basic",
                        "Advanced social media strategy",
                        "Weekly SEO updates",
                        "Google Ads management",
                        "Competitor analysis",
                        "Custom blog content",
                        "Monthly performance meeting",
                        "Dedicated account manager",
                    ],
                },
                {
                    title: "Premium",
                    price: 2999,
                    billingCycle: "mo",
                    description: "Comprehensive plan for large-scale businesses.",
                    services: [
                        "Everything in Standard",
                        "Complete SEO optimization",
                        "Custom PPC campaigns",
                        "Brand reputation management",
                        "Advanced analytics",
                        "A/B testing for ads",
                        "Unlimited content revisions",
                        "24/7 support",
                    ],
                },
            ],
            websiteDesignPlans: [
                {
                    title: "WordPress",
                    price: 1999,
                    description: "Efficient and customizable WordPress websites.",
                    services: [
                        "Responsive design",
                        "SEO optimization",
                        "Theme customization",
                        "Plugin integration",
                        "Blog setup",
                        "Contact form design",
                        "Basic eCommerce integration",
                        "Training for website management",
                    ],
                },
                {
                    title: "Shopify",
                    price: 2999,
                    description: "Tailored Shopify eCommerce stores.",
                    services: [
                        "Responsive Shopify theme",
                        "Product catalog setup",
                        "Payment gateway integration",
                        "Custom page designs",
                        "Third-party app integration",
                        "SEO-friendly architecture",
                        "Shipping and tax configuration",
                        "Training for store management",
                    ],
                },
                {
                    title: "Custom-Built",
                    price: "4999+",
                    description: "Custom solutions for unique business needs.",
                    services: [
                        "Custom UI/UX design",
                        "Tailored backend development",
                        "API integration",
                        "Scalable architecture",
                        "High-security features",
                        "Custom animations",
                        "Performance optimization",
                        "Ongoing support and updates",
                    ],
                },
            ],
            seoPlans: [
                {
                    title: "Starter",
                    price: 1999,
                    billingCycle: "mo",
                    description: "SEO basics for small businesses.",
                    services: [
                        "Keyword research",
                        "On-page optimization",
                        "Meta tag creation",
                        "Monthly SEO audit",
                        "Basic backlink building",
                        "Google My Business setup",
                        "Monthly performance report",
                        "Initial strategy meeting",
                    ],
                },
                {
                    title: "Growth",
                    price: 2999,
                    billingCycle: "mo",
                    description: "Advanced strategies for growth.",
                    services: [
                        "Everything in Starter",
                        "Competitor analysis",
                        "Content creation",
                        "Schema markup",
                        "Local SEO strategies",
                        "Social signal optimization",
                        "Weekly analytics updates",
                        "Dedicated SEO expert",
                    ],
                },
                {
                    title: "Elite",
                    price: 3999,
                    billingCycle: "mo",
                    description: "Full-scale SEO for market leaders.",
                    services: [
                        "Everything in Growth",
                        "Enterprise-level strategies",
                        "Custom content campaigns",
                        "Video SEO",
                        "Voice search optimization",
                        "International SEO",
                        "Weekly strategy meetings",
                        "24/7 priority support",
                    ],
                },
            ],
            automationPlans: [
                {
                    title: "Sales Process",
                    price: 999,
                    description: "Automate your sales funnel efficiently.",
                    services: [
                        "Lead tracking",
                        "Sales pipeline management",
                        "Automated CRM updates",
                        "Task scheduling",
                        "Follow-up reminders",
                        "Custom dashboard setup",
                        "Sales forecasting",
                        "Integration with third-party tools",
                    ],
                },
                {
                    title: "Email Outreach",
                    price: 1499,
                    description: "Streamline email campaigns.",
                    services: [
                        "Personalized email templates",
                        "Automated sequences",
                        "Email scheduling",
                        "A/B testing",
                        "Real-time analytics",
                        "List segmentation",
                        "Reply tracking",
                        "SPAM score monitoring",
                    ],
                },
                {
                    title: "Custom Workflow",
                    price: 1999,
                    description: "Custom solutions for unique processes.",
                    services: [
                        "Custom workflow mapping",
                        "Third-party integrations",
                        "Data synchronization",
                        "Custom triggers and actions",
                        "Real-time notifications",
                        "Team collaboration tools",
                        "Advanced analytics",
                        "Dedicated support",
                    ],
                },
            ],
        };
    },
    methods: {
        toggleDMPrices() {
            this.isQuarterlyDM = !this.isQuarterlyDM;
            const quarterlyPrices = [2500, 5500, 8500];
            const monthlyPrices = [999, 1999, 2999];
            this.digitalMarketingPlans.forEach((plan, index) => {
                plan.price = this.isQuarterlyDM ? quarterlyPrices[index] : monthlyPrices[index];
                plan.billingCycle = this.isQuarterlyDM ? "quarter" : "mo";
            });
        },
        toggleSEOPrices() {
            this.isSixMonthlySEO = !this.isSixMonthlySEO;
            const monthlyPrices = [1999, 2999, 3999];
            const sixMonthlyPrices = [1599, 2399, 3199]; // 20% off
            this.seoPlans.forEach((plan, index) => {
                plan.price = this.isSixMonthlySEO ? sixMonthlyPrices[index] : monthlyPrices[index];
                plan.billingCycle = this.isSixMonthlySEO ? "mo" : "mo";
            });
        },
    },
};
</script>

<style>
.service-list {
    margin: 10px 0 20px;
    padding-left: 20px;
    list-style-type: disc;
}
</style>
