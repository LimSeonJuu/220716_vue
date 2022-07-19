<template>
    <div class="black-bg" v-if="open == true">
          <div class="white-bg">
              <img :src="roomdata[idx].image" class="room_img">
              <h4>{{ roomdata[idx].title }}</h4>
              <p>{{ roomdata[idx].content }}</p>
                <input type="text" v-modal="month">
                <!-- <input @input="month = $event.target.value"> -->
              <p>{{ month }}개월 선택함 : {{ roomdata[idx].price * month }}</p>


              <discount />
              <button @click="$emit('closeModal')">닫기</button>
              <!-- <button @click="open = false">닫기</button> -->
          </div>
      </div>
</template>

<script>
export default {
    name : 'Modal',
    data(){
        return{
            month : 1,
        }
    },
    props : {
        idx : Number,
        open : Boolean,
        roomdata : Object,
    }
}
</script>

<style>

</style>