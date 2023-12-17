<!-- 首页 -->
<template>
    <div>
        <div class="block" style="background-color: rgb(0, 0, 225);">
            <el-carousel height="150px">
            <el-carousel-item>
                <div style="background-image: url('https://i.imgur.com/nNadJgb.jpeg');"></div>
            </el-carousel-item>
            <el-carousel-item>
                <div style="background-image: url('https://i.imgur.com/QkqjBYz.jpeg');"></div>
            </el-carousel-item>
            <el-carousel-item>
                <div style="background-image: url('https://i.imgur.com/dxnuPxi.jpeg');"></div>
            </el-carousel-item>
            <el-carousel-item>
                <div style="background-image: url('https://i.imgur.com/24yCqhP.jpeg');"></div>
            </el-carousel-item>
            </el-carousel>
        </div>
        <div style="width: 100%;">
            <el-calendar v-model="value"></el-calendar>
        </div>

    </div>
</template>


<script>
export default {
    name: 'HomeView',
    data() {
      return {
        value: new Date()
      }
    }
}
</script>



<style scoped>
    .block div {
        width: 100%;
        height: 100%;
        background-size: cover;
        background-position: center;
    }
</style>