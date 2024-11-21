<template>
    <section id="lnk-3" class="pt-100 ws-wrapper content-section">
        <div class="container">
            <div class="bc-5-wrapper bg--04 hidd bg--fixed r-16">
                <div class="section-overlay">
                    <!-- SECTION TITLE -->
                    <div class="row justify-content-center">
                        <div class="col-md-11 col-lg-9">
                            <div class="section-title wow fadeInUp mb-60">
                                <!-- Title -->
                                <h2 class="s-50 w-700">Build a customer-centric marketing strategy</h2>
                                <!-- Text -->
                                <p class="p-xl">Crafting a marketing strategy centered around your customers' needs helps build stronger relationships and drive better results, fostering long-term business success.</p>
                            </div>
                        </div>
                    </div>
                    <!-- IMAGE BLOCK -->
                    <div class="row justify-content-center">
                        <div class="col">
                            <div class="bc-5-img bc-5-tablet img-block-hidden video-preview wow fadeInUp">
                                <!-- Play Icon -->
                                <a href="https://www.youtube.com/watch?v=sbVbkS9xP7g" target="_blank">
                                    <div class="video-thumbnail">
                                        <img class="img-fluid" src="/assets/images/tablet-02.png" alt="content-image" />
                                        <div class="play-icon">
                                            <!-- Play button -->
                                            <i class="fa fa-play-circle" style="font-size: 50px; color: white; z-index: 10;"></i>
                                        </div>
                                    </div>
                                </a>
                                <!-- Embed YouTube Video -->
                                <div class="video-container" style="display:none;">
                                    <iframe width="100%" height="500" src="https://www.youtube.com/embed/sbVbkS9xP7g" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- End section overlay -->
            </div>
            <!-- End content wrapper -->
        </div>
        <!-- End container -->
    </section>
</template>

<script>
export default {
    data() {
        return {
            isVideoVisible: false
        };
    },
    methods: {
        toggleVideo() {
            this.isVideoVisible = !this.isVideoVisible;
        }
    }
};
</script>

<style scoped>
.video-preview {
    position: relative;
}

.video-thumbnail {
    position: relative;
}

.play-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    cursor: pointer;
    z-index: 100; /* Ensure the play button is above the image */
}

.video-container iframe {
    display: block;
    width: 100%;
    height: 500px;
}
</style>
