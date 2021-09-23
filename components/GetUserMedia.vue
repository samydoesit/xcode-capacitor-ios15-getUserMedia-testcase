<template>
    <div>
        <video 
            ref="video"
            playsinline
            autoplay
            muted
        />
    </div>
</template>

<script>
    export default {
        async mounted () {
            const constraints = {
                audio: false,
                video: {
                width: { min: 360, ideal: 640, max: 1920 },
                height: { min: 240, ideal: 480, max: 1080 },
                facingMode: { exact: "environment" }
                }
            };

            const stream = await navigator?.mediaDevices?.getUserMedia(constraints);
            this.$refs.video.srcObject = stream;
        },
    };
</script>