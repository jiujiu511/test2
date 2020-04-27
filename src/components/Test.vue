<template>
  <el-card>
    <!-- 第一题  -->
    <div class="box">
      <div class="left">
        <img :src="list.car.carTypeImage" alt />
        <p>{{list.car.carHeight}}米 {{list.car.loadingType.desc}}</p>
      </div>

      <div class="center">
        <h3>
          {{list.startAddress.province.name + list.startAddress.city.name + list.startAddress.district.name }}
          <span
            class="f"
          >
            ===>
            <span class="hour">{{list.hoursLength}}h</span>
            <span class="distance">{{list.distance}}km</span>
          </span>
          {{list.endAddress.province.name + list.endAddress.city.name + list.endAddress.district.name }}
        </h3>
        <p>
          <span>载货体积：{{list.car.carLong+'*'+list.car.carWidth+'*'+list.car.carHeight}}m</span>
          <span>载货重量：{{list.car.carLoad}}吨</span>
        </p>
      </div>

      <div class="right">
        <div>
          <h2 style="color:orange">一口价:￥{{list.price}}</h2>
          <p>累计已发：{{list.usageCount}}车</p>
        </div>

        <div class="bottom">
          <el-button type="primary">立即用车</el-button>
        </div>
      </div>
    </div>
  </el-card>
</template>

<script>
import list from "../utils/test.json";
export default {
  data() {
    return {
      list: []
    };
  },
  created() {
    this.list = list;
  }
};
</script>

<style lang="less" >
.box {
  display: flex;
  justify-content: space-around;
  border-bottom: 1px solid #eee;
  margin-top: 10px;
  .left {
    img {
      width: 100px;
      height: 80px;
      border: 1px solid red;
      border-radius: 10px;
    }
    p {
      text-align: center;
    }
  }
  .center {
    h3 {
      .f {
        position: relative;
        color: #aaa;
        .hour {
          position: absolute;
          left: 3px;
          top: -6px;
          font-size: 14px;
        }
        .distance {
          position: absolute;
          left: 3px;
          bottom: -10px;
          font-size: 14px;
        }
      }
    }
    p {
      display: flex;
      justify-content: space-between;
      font-size: 14px;
    }
  }
  .right {
    display: flex;
    align-items: center;
    .bottom {
      margin-left: 20px;
    }
  }
}

// 第二题
// div {
//   width: 300px;
//   height: 300px;
//   border: #000 solid 1px;
//   margin: 50px auto;
//   overflow: hidden;
// }
// div img {
//   cursor: pointer;
//   transition: all 0.6s;
// }
// div img:hover {
//   transform: scale(1.4);
// }
</style>