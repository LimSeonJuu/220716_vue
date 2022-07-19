<template>
    <div>
        <img :src="roomInfo.image" class="room_img">
        <!-- <h4 @click="$emit('openModal', roomInfo.id)">{{ roomInfo.title }}</h4> -->
        <h4 @click="send">{{ roomInfo.title }}</h4>
        <p>{{ roomInfo.price }}</p>
    </div>

    <!-- <div v-for="(roomInfo, i) in roomdata" :key="i">
        <img :src="roomInfo.image" class="room_img">
        <<h4 @click="open = true; idx = i">{{ roomInfo.title }}</h4>>
        <p>{{ roomInfo.price }}</p>
    </div> -->
</template>

<script>
export default {
    name : 'Card',
    props : {
        roomInfo : Object,
    },
    methods : {
        send(){
            this.$emit('openModal', this.roomInfo.id)
        }
    }
}
</script>

<style>

</style>