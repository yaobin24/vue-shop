<template>
  <section class="goods-list">
    <img v-if="promotionSpus" v-lazy="promotionSpus[0].imgUrl" class="goods-hot" @click="open(promotionSpus[0].link)">
    <h2 class="goods-list-title">{{title}}</h2>
    <section class="goods-list_box">
      <ul>
        <li v-for="item in commoditySpus" :key="item.skuId" @click="open(item.skuId)">
          <div class="list">
            <div class="goods-image">
              <img :src="item.imgUrl" alt="图片">
            </div>
            <p class="goods-name">{{item.name | text(10)}}</p>
            <p class="selling-point">{{item.brief | text(10)}}</p>
            <p class="goods-price">￥{{item.price}}</p>
          </div>
        </li>
      </ul>
    </section>
  </section>
</template>

<script>
  export default {
    props: [
      'title',
      'promotionSpus',
      'commoditySpus',
    ],
    data(){
      return {}
    },
    methods: {
      open: function (id) {
//        this.$router.push({ path: "goodDetail", query: { id: id ,source_type:'首页爆款专区'} });
      }
    },
    computed: {},
    created(){
    },
    mounted(){
    },
    watch: {},
    components: {},
  }
</script>

<style lang="scss">
  @import '../../assets/scss/mixin';

  .goods-list{
    padding-bottom: 2rem;
  }
  .goods-list-title {
    margin: .5rem;
    height: 1.1rem;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.1rem;
    color: #333;
    text-align: center;
  }

  .goods-list-title:before, .goods-list-title:after {
    position: relative;
    margin: 0 .1rem;
    display: inline-block;
    content: ' ';
    height: 1px;
    width: .8rem;
    background-color: #9c9c9c;
    vertical-align: middle;
  }

  .goods-hot {
    border: 0;
    vertical-align: middle;
    width: 100%;
  }

  .goods-list_box {
    padding-bottom: 2rem;
    .list {
      height: 7rem;
      background: white;
      float: left;
      width: 50%;
      border-right: 1px solid #f4f4f4;
      border-top: 1px solid #f4f4f4;

      span {
        display: block;
        color: red;
        padding-left: 0.5rem;
        padding-top: 0.1rem;
      }
    }

    ul {
      overflow-x: auto;
      padding-bottom: 1.5rem;
      li {
        list-style: none;
      }

    }
    .goods-image {
      width: 100%;
      background: white;
      img {
        width: 3rem;
        height: 3rem;
        display: block;
        margin: auto;
        margin-top: .5rem;
        margin-bottom: .2rem
      }
    }

    .goods-name {
      height: 0.9rem;
      line-height: 0.5rem;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      font-size: 0.3rem;
      font-weight: 900;
      text-align: center;
      padding-top: 0.3rem;
    }
    .selling-point {
      height: 1rem;
      font-size: 0.1rem;
      text-align: center;
    }

    .goods-price {
      font-size: 0.33rem;
      color: red;
      margin: auto;
      text-align: center;
    }
  }


</style>
