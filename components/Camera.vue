<template>
    <div>
        <QrcodeStream ref="stream" style="height: 80vh; width: 100vw; opacity:0;">
            
        </QrcodeStream>
    </div>
</template>

<script>
    import { QrcodeStream } from 'vue-qrcode-reader'
    export default {
        components: {
            QrcodeStream,
        },
        mounted () {
            setTimeout(() => {
                this.$refs.stream.$el.style.opacity = 1;
            }, 3000);
        },
    }
</script>

<style lang="scss" scoped>

</style>