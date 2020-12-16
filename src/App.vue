<template>
  <div id="app">
    <div class="liDemo" v-for="item in list" :key="item.imgUrl">
      <SlideToDel
        @onClick="onClick"
        @onSlide="onSlide"
        :sliderId="item.id"
        :curSlideID="curSlideID"
        :handles="handles"
        :sensitivity="sensitivity"
      >
        <div class="df fg1 f-ac">
          <img :src="item.imgUrl" alt="" class="df f-js img" />
          <p class="df fg1">{{ item.title }}</p>
        </div>
      </SlideToDel>
    </div>
  </div>
</template>

<script>
import SlideToDel from "@/components/SlideToDel.vue";
export default {
  name: "App",
  components: {
    SlideToDel,
  },
  data: function () {
    return {
      list: [
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608116221510&di=694852c91e552e68a670f82815d5ad97&imgtype=0&src=http%3A%2F%2Fattach.bbs.miui.com%2Fforum%2F201305%2F30%2F220025pxfkhykvkgkvuktq.jpg",
          title: 0,
          id: 0,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122319754&di=baef1cc964e443464c02ea2ac9588b63&imgtype=0&src=http%3A%2F%2Fattach.bbs.miui.com%2Fforum%2F201408%2F07%2F213601f2xz7usscm2z1mjh.jpg",
          title: 1,
          id: 1,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122326450&di=65f10f53b82d30037ce3c4bf17b4068c&imgtype=0&src=http%3A%2F%2Ff.hiphotos.baidu.com%2Fzhidao%2Fpic%2Fitem%2F241f95cad1c8a7863cb5bacd6709c93d71cf5052.jpg",
          title: 2,
          id: 2,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122346127&di=b2e344cb29f3cd4b725b3b4bd18deb76&imgtype=0&src=http%3A%2F%2Fbenyouhuifile.it168.com%2Fforum%2F201304%2F06%2F11435052yrezzae1bua8ee.jpg",
          title: 3,
          id: 3,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122467284&di=3d3684c0fcd46a4936a375fb841929dc&imgtype=0&src=http%3A%2F%2Fattach.bbs.miui.com%2Fforum%2F201403%2F01%2F134104shkenreehh21nol1.jpg",
          title: 4,
          id: 4,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122469971&di=c54f426772a69fa37150fce4cc1f5e68&imgtype=0&src=http%3A%2F%2Fattachments.gfan.com%2Fforum%2Fattachments2%2Fday_100430%2F10043015437962673bf6152eff.jpg",
          title: 5,
          id: 5,
        },
        {
          imgUrl:
            "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1608122484081&di=215184f79d0ecc8597ea5c14f4bbb641&imgtype=0&src=http%3A%2F%2Fimg4.imgtn.bdimg.com%2Fit%2Fu%3D3579831024%2C633721272%26fm%3D214%26gp%3D0.jpg",
          title: 6,
          id: 6,
        }
      ],
      nihao: "bushiba",
      curSlideID: null,
      handles: [
        { title: "回复", id: 0 },
        // { title: "置顶", id: 1 },
        { title: "删除", id: 2 },
      ],
      sensitivity: 3
    };
  },
  methods: {
    onClick(val) {// 监听用户操作的，返回的val和handles对应
      console.log("csx click -> " + val);
    },
    onSlide(val) {// 监听当前滑动的哪个slider组件
      console.log("csx onSlide val:", val);
      this.curSlideID = val;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

html,
body,
#app {
  height: 100%;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: rgba(220, 220, 220);
}

ul,
li {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.liDemo {
  color: #000;
  margin-bottom: 3px;
  height: 60px;
  line-height: 60px;
}

.img {
  width: 20%;
  height: auto;
  margin: 5px;
}

.df {
  display: flex;
  display: -webkit-flex;
}
.fg1 {
  flex-grow: 1;
}
.f-ac {
  align-content: center;
  -webkit-align-content: center;
}
.f-js {
  justify-content: flex-start;
  -webkit-justify-content: flex-start;
}
.f-jc {
  justify-content: center;
  -webkit-justify-content: center;
}
</style>
