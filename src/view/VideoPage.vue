<template>
    <div class="video-panel">
        <video-player ref="videoPlayer" :options="videoOptions" class="vjs-custom-skin videoPlayer"></video-player>
    </div>
</template>

<script>
import config from '@/request/config';
import { setTimeout } from 'timers';


//引入vuex
import { mapMutations, mapState } from 'vuex'

import { videoPlayer } from 'vue-video-player'
import 'videojs-flash'

import {
    get_baidu,
    post_baidu
} from '@/request/api';

export default {
    name: 'HomePage',
    props: [],
    data() {
        return {
            msg: 'Welcome to Your Vue.js App',
            videoOptions: {
                height: '260',
                sources: [{
                    type: 'rtmp/mp4',
                    src: 'rtmp://202.69.69.180:443/webcast/bshdlive-pc',//'rtmp://58.200.131.2:1935/livetv/hunantv'//'rtmp://58.200.131.2:1935/livetv/hunantv'
                }],
                techOrder: ['flash'],
                muted: true, // 默认静音
                preload: 'auto', // 视频预加载
                autoplay: true,
                controls: true,
                notSupportedMessage: '此视频暂无法播放，请稍后再试'
            }
        }
    },

    mounted() {
        this.$message('欢迎使用基础模板!');
    },
    components:{videoPlayer},
    methods: {

    },
}
</script>

<style lang="scss" scope>
.video-panel{
    height:100%;
}
</style>
