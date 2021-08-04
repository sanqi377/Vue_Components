<template>
    <div class="music">
        <div class="main">
            <div class="player">
                <div class="top">
                    <div class="content" id="music">
                        <div class="left">
                            <img :src="playerIng.picurl" />
                        </div>
                        <div class="right">
                            <div class="title">{{ playerIng.name }}</div>
                            <div class="author">
                                {{ playerIng.artistsname }}
                            </div>
                        </div>
                    </div>
                </div>
                <div class="bottom">
                    <div>
                        <div class="prve" @click="prve()">
                            <svg viewBox="0 0 36 20">
                                <path
                                    d="M1.69813738,11.0254725 C0.75331072,10.4595484 0.761328762,9.53720142 1.69813738,8.97607983 L16.2885768,0.236823587 C17.2334034,-0.329100579 17.9993368,0.11180583 17.9993368,1.20339155 L17.9993368,18.7981608 C17.9993368,19.8979057 17.2253854,20.3258504 16.2885768,19.7647288 L1.69813738,11.0254725 Z"
                                ></path>
                                <path
                                    d="M19.6988006,8.97607983 C18.7539739,9.542004 18.761992,10.4643509 19.6988006,11.0254725 L34.28924,19.7647288 C35.2340667,20.3306529 36,19.8897465 36,18.7981608 L36,1.20339155 C36,0.103646637 35.2260486,-0.324298001 34.28924,0.236823587 L19.6988006,8.97607983 Z"
                                ></path>
                            </svg>
                        </div>
                        <div class="player" @click="player()">
                            <svg viewBox="0 0 64 64" v-show="!isPlayer">
                                <path
                                    d="M51.109 30.335l-36-24A2 2 0 0 0 12 8v48a2.003 2.003 0 0 0 2 2c.388 0 .775-.113 1.109-.336l36-24a2 2 0 0 0 0-3.329z"
                                ></path>
                            </svg>
                            <svg viewBox="0 0 100 100" v-show="isPlayer">
                                <path
                                    d="M22.537 8.046h17.791c1.104 0 2.003.898 2.003 1.993v79.912a2.005 2.005 0 0 1-2.003 2.003h-17.79a2.005 2.005 0 0 1-2.003-2.003V10.04c0-1.095.898-1.993 2.002-1.993zM59.672 8.046h17.8c1.095 0 1.993.898 1.993 1.993v79.912a2.003 2.003 0 0 1-1.993 2.003h-17.8a1.997 1.997 0 0 1-1.993-2.003V10.04c0-1.095.889-1.993 1.993-1.993z"
                                ></path>
                            </svg>
                        </div>
                        <div class="next" @click="next()">
                            <svg viewBox="0 0 36 20">
                                <path
                                    d="M34.3018626,8.97607983 C35.2466893,9.542004 35.2386712,10.4643509 34.3018626,11.0254725 L19.7114232,19.7647288 C18.7665966,20.3306529 18.0006632,19.8897465 18.0006632,18.7981608 L18.0006632,1.20339155 C18.0006632,0.103646637 18.7746146,-0.324298001 19.7114232,0.236823587 L34.3018626,8.97607983 Z"
                                ></path>
                                <path
                                    d="M16.3011994,8.97607983 C17.2460261,9.542004 17.238008,10.4643509 16.3011994,11.0254725 L1.71075999,19.7647288 C0.765933339,20.3306529 0,19.8897465 0,18.7981608 L0,1.20339155 C0,0.103646637 0.773951381,-0.324298001 1.71075999,0.236823587 L16.3011994,8.97607983 Z"
                                ></path>
                            </svg>
                        </div>
                    </div>
                </div>
                <audio :src="playerIng.url" ref="audio"></audio>
                <div class="process"></div>
                <div
                    class="processActive"
                    :style="'width: ' + Number(Process_Now) + '%'"
                ></div>
            </div>
            <div class="list">
                <ul>
                    <div class="item">
                        <div class="sort">
                            <svg
                                t="1628080861623"
                                class="icon"
                                viewBox="0 0 1024 1024"
                                version="1.1"
                                xmlns="http://www.w3.org/2000/svg"
                                p-id="1407"
                                width="200"
                                height="200"
                                @click="changeType(1)"
                            >
                                <path
                                    d="M958.708971 342.196663 958.708971 834.519508c0 27.386744-22.224164 49.923016-49.634444 49.923016L177.627537 884.442524c-27.41028 0-49.634444-22.248723-49.634444-49.634444s22.224164-49.634444 49.634444-49.634444l681.812547 0L859.440084 388.099109 235.564064 388.099109l68.228941 69.366857c19.472494 19.273972 19.623943 52.514027 0.333598 71.970148-9.707083 9.788947-22.485107 14.684444-35.263132 14.684444-12.626575 0-25.254174-4.797259-34.930557-14.373359L79.995939 377.36872c-9.4093-9.31004-14.705933-22.057365-14.705933-35.289738s5.29561-26.03905 14.705933-35.349089l153.936975-152.583141c19.47454-19.261693 50.901297-19.594267 70.192665-0.13917 19.290345 19.455097 19.138896 49.910737-0.333598 69.185732l-68.228941 65.637929 673.511487 0C936.485831 288.830221 958.708971 314.810942 958.708971 342.196663z"
                                    p-id="1408"
                                    :fill="type == 1 ? '#176AFD' : ''"
                                ></path>
                            </svg>
                            <svg
                                t="1628080923423"
                                class="icon"
                                viewBox="0 0 1024 1024"
                                version="1.1"
                                xmlns="http://www.w3.org/2000/svg"
                                p-id="1544"
                                width="200"
                                height="200"
                                @click="changeType(2)"
                            >
                                <path
                                    d="M753.564731 337.471035c-45.8697 0-160.259984 113.849978-243.789399 194.548928C383.134027 654.383848 263.508509 773.284865 167.764911 773.284865l-58.892295 0c-24.068162 0-43.581588-19.526729-43.581588-43.581588s19.513426-43.581588 43.581588-43.581588l58.892295 0c60.504002 0 183.002964-121.68134 281.432741-216.784348 119.79641-115.744117 223.254713-219.029482 304.368102-219.029482l56.209186 0-59.641355-57.828057c-17.033955-16.993023-17.060561-42.902112-0.057305-59.927881 17.002232-17.030885 44.596707-17.064654 61.631686-0.065492l134.207631 133.874033c8.192589 8.172123 12.794397 19.238157 12.794397 30.803563 0 11.564383-4.601808 22.604834-12.794397 30.776957L811.706943 461.72599c-8.505721 8.486278-19.646456 12.522198-30.78719 12.522198-11.166317 0-22.333658-4.676509-30.844495-13.199627-17.003256-17.025769-16.975627-45.432749 0.057305-62.425771l59.641355-61.151755L753.564731 337.471035zM811.706943 561.66105c-17.034978-16.999163-44.629453-16.972557-61.631686 0.058328-17.003256 17.024745-16.975627 46.257533 0.057305 63.250556l59.641355 61.150732-56.209186 0c-35.793204 0-95.590102-52.946886-154.87637-108.373243-17.576307-16.435321-45.161572-16.3422-61.594847 1.226944-16.444531 17.568121-15.523555 46.393633 2.053776 62.823837 90.322122 84.458577 151.246703 131.484613 214.417441 131.484613l56.209186 0-59.641355 57.824987c-17.033955 16.993023-17.060561 43.736107-0.057305 60.761875 8.511861 8.523117 19.678178 12.369725 30.844495 12.369725 11.140735 0 22.281469-4.453429 30.78719-12.939707L945.914574 757.311055c8.192589-8.173147 12.794397-19.315928 12.794397-30.881334 0-11.564383-4.601808-22.682605-12.794397-30.855752L811.706943 561.66105zM108.871593 337.471035l58.892295 0c45.932122 0 114.40154 58.455343 168.915108 107.942431 8.352225 7.576559 18.832927 12.140505 29.29214 12.140505 11.852956 0 23.673166-4.394077 32.270984-13.857613 16.182564-17.807574 14.859429-46.823422-2.958378-62.998823-85.247546-77.381391-156.561755-130.388652-227.519854-130.388652l-58.892295 0c-24.068162 0-43.581588 19.526729-43.581588 43.581588S84.804455 337.471035 108.871593 337.471035z"
                                    p-id="1545"
                                    :fill="type == 2 ? '#176AFD' : ''"
                                ></path>
                            </svg>
                            <svg
                                t="1628080939857"
                                class="icon"
                                viewBox="0 0 1024 1024"
                                version="1.1"
                                xmlns="http://www.w3.org/2000/svg"
                                p-id="1681"
                                width="200"
                                height="200"
                                @click="changeType(3)"
                            >
                                <path
                                    d="M958.708971 326.351789l0 537.595958c0 29.90203-24.24417 54.157457-54.146201 54.157457L119.43723 918.105205c-29.90203 0-54.146201-24.255427-54.146201-54.157457L65.291029 326.351789c0-29.90203 24.24417-58.006112 54.146201-58.006112l300.952306 0-73.492828-72.063269c-21.070898-21.217231-20.958334-53.578266 0.258896-74.649164 21.210068-21.077038 55.494918-20.973684 76.57298 0.243547l165.229159 166.310793c20.972661 21.116947 20.972661 55.134715 0 76.251661L423.727561 530.661012c-10.582009 10.654664-24.495904 15.748682-38.415938 15.748682-13.794168 0-27.595498-5.724375-38.157042-16.213263-21.217231-21.070898-21.329794-56.319703-0.258896-77.536934l73.599252-76.020394L173.58343 376.639103l0 433.172677 676.832116 0L850.415546 376.639103 736.709855 376.639103c-29.90203 0-54.146201-24.245194-54.146201-54.146201s24.24417-54.146201 54.146201-54.146201l167.852916 0C934.464801 268.345678 958.708971 296.449759 958.708971 326.351789z"
                                    p-id="1682"
                                    :fill="type == 3 ? '#176AFD' : ''"
                                ></path>
                            </svg>
                        </div>
                        <div class="volume">
                            <svg
                                t="1628081020398"
                                class="icon"
                                viewBox="0 0 1024 1024"
                                version="1.1"
                                xmlns="http://www.w3.org/2000/svg"
                                p-id="1818"
                                width="200"
                                height="200"
                            >
                                <path
                                    d="M508.068458 68.448952c-15.960507-6.565533-33.750685-2.663666-45.892213 9.56382l-208.498638 210.654744L150.309354 288.667515c-23.503297 0-42.402739 18.642592-42.402739 42.141796L107.906615 693.241854c0 23.49818 18.899442 42.141796 42.402739 42.141796l103.369276 0 209.027687 210.654744c8.151657 8.206916 19.082614 12.671601 30.211069 12.671601 5.455245 0 9.903557-0.997724 15.151072-3.158946 15.939017-6.569626 25.281803-22.049179 25.281803-39.289841L533.350261 107.788935C533.351284 90.549296 524.007475 75.018577 508.068458 68.448952zM448.26235 813.019845 300.55424 663.061484c-7.990998-8.045233-17.817808-12.767791-29.15911-12.767791l-78.399581 0L192.995549 373.755426l78.399581 0c11.341303 0 21.168112-4.722558 29.15911-12.767791L448.26235 211.029274 448.26235 813.019845zM672.196539 692.103938c-8.410554 9.432837-20.074198 14.242376-31.79003 14.242376-10.07445 0-20.189831-3.553942-28.299533-10.783601-17.550725-15.639189-19.098987-42.534745-3.460822-60.07626 105.97666-118.880551 11.050684-234.291071-0.124843-247.058862-15.425318-17.629519-13.767562-44.48312 3.792373-59.987233 17.58654-15.510252 44.295855-13.963013 59.881832 3.505847C727.72011 394.229736 799.178605 549.661761 672.196539 692.103938zM800.394293 805.935496c-8.4126 9.431813-20.075221 14.242376-31.791054 14.242376-10.07445 0-20.189831-3.553942-28.299533-10.783601-17.550725-15.639189-19.097964-42.534745-3.459798-60.07626 208.05043-233.387491 8.526187-464.919728-0.067538-474.664673-15.523555-17.59268-13.912871-44.467771 3.641947-60.030212 17.567098-15.551184 44.3593-14.023388 59.977 3.490497C803.01191 221.048465 1059.402301 515.38612 800.394293 805.935496z"
                                    p-id="1819"
                                ></path>
                            </svg>
                            <input
                                id="volume"
                                type="range"
                                min="0"
                                max="100"
                                v-model="volumes"
                                @input="volume"
                            />
                        </div>
                    </div>
                    <li v-for="(item, idx) in data" :key="idx">
                        <div class="info">
                            {{ item.name }} - {{ item.artistsname }}
                        </div>
                        <div class="btn">
                            <div class="play" @click="call(idx)">
                                <svg
                                    t="1628081931574"
                                    class="icon"
                                    viewBox="0 0 1024 1024"
                                    version="1.1"
                                    xmlns="http://www.w3.org/2000/svg"
                                    p-id="2854"
                                    width="200"
                                    height="200"
                                >
                                    <path
                                        d="M837.818182 93.090909c51.2 0 93.090909 41.890909 93.090909 93.090909v651.636364c0 51.2-41.890909 93.090909-93.090909 93.090909H186.181818c-51.2 0-93.090909-41.890909-93.090909-93.090909V186.181818c0-51.2 41.890909-93.090909 93.090909-93.090909h651.636364m0-93.090909H186.181818C83.781818 0 0 83.781818 0 186.181818v651.636364c0 102.4 83.781818 186.181818 186.181818 186.181818h651.636364c102.4 0 186.181818-83.781818 186.181818-186.181818V186.181818c0-102.4-83.781818-186.181818-186.181818-186.181818z"
                                        fill="#1D2633"
                                        p-id="2855"
                                    ></path>
                                    <path
                                        d="M460.8 721.454545l230.4-162.90909c32.581818-23.272727 32.581818-72.145455 0-95.418182l-230.4-162.909091c-39.563636-27.927273-93.090909 0-93.090909 48.872727v325.818182c0 46.545455 53.527273 74.472727 93.090909 46.545454z"
                                        fill="#176AFD"
                                        p-id="2856"
                                    ></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
var time;
export default {
    name: "Music",
    data() {
        return {
            // 默认数据
            data: [
                {
                    picurl: "http://p2.music.126.net/4RykM52XvUd5avvhbzFFKA==/109951166031360436.jpg", // 背景图片
                    name: "高考那个夏天", // 名称
                    text: "....", // 说明
                    artistsname: "高宇Slient", // 作者
                    url: "http://music.163.com/song/media/outer/url?id=1832399395", // 媒体文件地址
                },
                {
                    picurl: "http://p1.music.126.net/L-6FYIDjMmrrOI-a_hT8CQ==/109951165554944740.jpg", // 背景图片
                    name: "爱人错过", // 名称
                    text: "....", // 说明
                    artistsname: "初月", // 作者
                    url: "http://music.163.com/song/media/outer/url?id=1815759242", // 媒体文件地址
                },
                {
                    picurl: "http://p2.music.126.net/qn7Fq7mDk-ADKV4-CfHRpw==/109951165642867823.jpg", // 背景图片
                    name: "《凄》", // 名称
                    text: "....", // 说明
                    artistsname: "527", // 作者
                    url: "http://music.163.com/song/media/outer/url?id=1813388659", // 媒体文件地址
                },
                {
                    picurl: "http://p2.music.126.net/dW3bq2cQcWu-5ADXWHEWAA==/109951165423355433.jpg", // 背景图片
                    name: "If", // 名称
                    text: "....", // 说明
                    artistsname: "七元", // 作者
                    url: "http://music.163.com/song/media/outer/url?id=1406665350", // 媒体文件地址
                },
                {
                    picurl: "http://p2.music.126.net/ZWp23Ah6BnZLxDQZ804zAQ==/109951166163095619.jpg", // 背景图片
                    name: "千年の恋", // 名称
                    text: "....", // 说明
                    artistsname: "芝麻Mochi", // 作者
                    url: "http://music.163.com/song/media/outer/url?id=1859954221", // 媒体文件地址
                },
            ],
            // 播放中数据
            playerIng: {
                picurl: "http://p3.music.126.net/uGhXUa8-QfqCiYhw3_xHpg==/109951165762718245.jpg", // 背景图片
                name: "狮子座", // 名称
                text: "....", // 说明
                artistsname: "高宇Slient", // 作者
                url: "http://music.163.com/song/media/outer/url?id=1823333143", // 媒体文件地址
            },
            isPlayer: false, // 是否播放中
            Process_Now: null, // 播放进度
            volumes: 40, // 音量
            type: 1, // 1：顺序播放，2：随机播放，3：单曲循环
        };
    },
    mounted() {
        this.getMusic();
    },
    methods: {
        // 这里获取数据
        getMusic() {
            // 设置默认声音大小
            var aud = this.$refs.audio;
            aud.volume = Number(this.volumes) / 100;
            // example
            // this.$http.get({}).then((res) => {
            // this.data = res;
            // 插入背景图片
            this.changeBg();
            // });
        },

        // 播放 / 暂停
        player() {
            this.isPlayer = !this.isPlayer; // 改变播放状态同时改变播放 / 暂停 图标
            var aud = this.$refs.audio; // 获取 audio 实例
            if (this.isPlayer) {
                aud.play(); // 播放
                this.TimeSpan(); // 定时器 主要用于播放进度
            } else {
                aud.pause(); // 暂停
                clearInterval(time); // 清除定时器
            }
        },
        // 计算长度
        TimeSpan() {
            time = setInterval(() => {
                var aud = this.$refs.audio;
                this.Process_Now = (
                    (aud.currentTime / aud.duration) *
                    100
                ).toFixed(2); // 将 Process_Now 转换为整数并给它加一个px单位
                if (aud.ended) {
                    this.changeType();
                }
            }, 1000);
        },
        // 音量调节
        volume() {
            var aud = this.$refs.audio;
            var volume = Number(this.volumes) / 100;
            aud.volume = volume;
        },
        // 更换背景
        changeBg() {
            let s = document.createElement("style");
            s.innerText =
                ".content::after{background: url(" +
                this.playerIng.picurl +
                ");}";
            document.body.appendChild(s);
        },
        // 插播
        call(idx) {
            var aud = this.$refs.audio;
            this.data.forEach((item, index) => {
                if (idx == index) {
                    this.data.push(this.playerIng);
                    this.playerIng = item;
                    this.changeBg();
                    this.data.splice(idx, 1);
                    aud.autoplay = true;
                    this.isPlayer = true;
                    this.TimeSpan();
                }
            });
        },
        // 切换播放方式
        changeType(type) {
            if (type) {
                this.type = type;
            } else {
                // 如果歌曲播放完成，根据播放方式播放
                var aud = this.$refs.audio;
                this.Process_Now = null;
                this.TimeSpan();
                switch (this.type) {
                    // 顺序播放
                    case 1:
                        this.data.push(this.playerIng);
                        this.playerIng = this.data[0];
                        this.changeBg();
                        this.data.splice(0, 1);
                        aud.autoplay = true;
                        break;
                    // 随机播放
                    case 2:
                        var random = Math.floor(
                            Math.random() * (this.data.length - 0 + 1) + 0
                        );
                        this.data.push(this.playerIng);
                        this.playerIng = this.data[random];
                        this.changeBg();
                        this.data.splice(random, 1);
                        aud.autoplay = true;
                        break;
                    // 单曲循环
                    case 3:
                        aud.play();
                        console.log(this.playerIng);
                        break;
                }
                clearInterval(time);
            }
        },
        // 上一首
        prve() {
            console.log(this.data[this.data.length - 1]);
            var aud = this.$refs.audio;
            this.data.unshift(this.playerIng);
            this.playerIng = this.data[this.data.length - 1];
            this.changeBg();
            this.TimeSpan();
            this.data.splice(this.data.length - 1, 1);
            aud.autoplay = true;
            this.isPlayer = true;
        },
        // 下一首
        next() {
            var aud = this.$refs.audio;
            this.data.push(this.playerIng);
            this.playerIng = this.data[0];
            this.changeBg();
            this.TimeSpan();
            this.data.splice(0, 1);
            aud.autoplay = true;
            this.isPlayer = true;
        },
    },
};
</script>

<style scoped>
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    text-align: left;
}
ul li {
    padding: 10px 15px;
    font-size: 14px;
    border-bottom: 1px solid #ccc;

    display: flex;
    justify-content: space-between;
}
ul li:last-child {
    border-bottom: 0;
}
ul li .play {
    cursor: pointer;
    display: flex;
}
.music {
    width: 400px;
    margin: 0 auto;
    border-radius: 12px;
    background-color: #fff;
    position: relative;
}
.top {
    overflow: hidden;
    border-radius: 12px;
    border-bottom-right-radius: 0;
    border-bottom-left-radius: 0;
}
.buttom {
    height: 300px;
}
.content {
    width: 100%;
    height: 135px;
    display: flex;
    position: relative;
    justify-content: space-evenly;
}
.content::after {
    content: "";
    position: absolute;
    z-index: 1;
    filter: blur(0.6rem) brightness(0.7);
    background-position-x: center;
    background-position-y: center;
    background-size: cover;
    object-fit: cover;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    overflow: hidden;
}
.content .left {
    z-index: 2;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    width: 45%;
}
.content .left img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}
.content .right {
    z-index: 2;
    display: flex;
    justify-content: center;
    align-content: center;
    flex-wrap: wrap;
    width: 55%;
}
.content .right > div {
    width: 100%;
    margin-bottom: 10px;
}
.content .title {
    color: #fff;
    font-size: 20px;
    font-weight: 700;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.content .author {
    color: #cfcfcf;
}
.player {
    position: relative;
}
.bottom {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(255, 255, 255, 0.3);
    z-index: 5;
    display: none;
    border-radius: 12px;
    border-bottom-right-radius: 0;
    border-bottom-left-radius: 0;
}
.player:hover .bottom {
    display: block;
}
.bottom > div {
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 100%;
}
.bottom .player {
    cursor: pointer;
}
.bottom svg {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 35px;
    height: 35px;
}
.player svg {
    opacity: 0.8;
    width: 45px;
    height: 45px;
}
.list {
    border: 1px solid #ccc;
    border-bottom-right-radius: 12px;
    border-bottom-left-radius: 12px;
    background: #fff;
}
.process {
    position: absolute;
    bottom: 0;
    height: 3px;
    background: #000;
    width: 100%;
    z-index: 99;
}
.processActive {
    position: absolute;
    bottom: 0;
    height: 3px;
    background: #fff;
    width: auto;
    z-index: 999;
}
.list .item {
    padding: 5px 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #ccc;
}
.list .item svg {
    width: 20px;
    height: 20px;
}
.list .item > div {
    display: flex;
    align-items: center;
}
.list .item .sort svg {
    margin: 0 8px;
    cursor: pointer;
}
.list .item .sort svg:first-child {
    margin-left: 0;
}
.list .item .sort svg:last-child {
    margin-right: 0;
}

.list .play svg {
    width: 20px;
    height: 20px;
}
</style>