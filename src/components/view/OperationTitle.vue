<template>
    <div class="title-container">
      <img v-if="items.title_mode == 1" class="title-image" :src="items.image" @click="moreClick(items)">
      <div v-else-if="items.title_mode == 2" class="title-text">{{items.slot_name}}</div>
      <div v-if="showMore()" class="more-container" >
        <img src="../../assets/img/more.png" class="more-image" @click="moreClick(items)">
        <div class="more">更多</div>
      </div>
    </div>
</template>

<script>

export default {
  name: "operationTitle",
  props: ["items"],
  methods:{
      moreClick(items){
          console.log("点击 title Item", items.link_h5);
          window.location.href = items.link_h5;
      },
      showMore(){
        console.log("link_h5",this.items.link_h5)
        console.log("name",this.items.slot_name)
        if(this.items.link_h5 && this.items.slot_name && this.items.title_mode == 2){
          return true;
        }else{
          return false;
        }
      }
  }
}
</script>

<style>
.title-image{
  margin-top: 20px;
  height: 50px;
  width: 100%;
}
.title-container{
  display: flex;
  /* padding-top: 20px; */
}
.title-text{
  width: 80%;
  margin-top: 20px;
  padding: 10px 20px;
  background-color: white;
  text-align: left;
  color: #333333;
  font-weight: 600;
  font-size: 36px;
  font-family:PingFang SC;
}

.more-container{
  margin-top: 20px;
  display: flex;
  width: 20%;
  flex-direction: row-reverse; 
  padding-right: 15px;
  align-items: center;
}
.more{
  text-align: right;
  /* align-items: center; */
  /* margin: auto 0; */
  color: #666666
}
.more-image{
  width: 40px;
  height: 40px;
  /* align-items: center; */
  /* margin: auto 0; */
}
</style>