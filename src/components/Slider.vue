<template>
<div class="slider">
    <button @click="prev" type="button" class="btn btn-left">
        <img src="../assets/chevronleft.png"  class="icone">
    </button>
    <div class="container-slides" :style="{transform: `translateX(${index}px)`,transition: `${transition}`}">
    <img src="../assets/slide1.jpg" class="img-slider">
    <img src="../assets/slide2.jpg" class="img-slider">
    <img src="../assets/slide3.jpg" class="img-slider">
    </div>
    <button @click="next" type="button" class="btn btn-right">
        <img src="../assets/chevronright.png"  class="icone">
    </button>

</div>
</template>
<script>
export default {
    name:'Slider',
    data: function(){
        return {
            index: 0,
            transition: "transform 0.2s ease"
        }
    },
    methods: {
        next(){
            if(this.index === -1500) {
                this.transition = "none";
                this.index = 0;
            } else {
                this.transition = "transform 0.2s ease";
                this.index -= 500;
            }
        },
        prev(){
            if(this.index === 0){
                this.transition = "none";
                this.index = -1500;


            } else {
                this.transition = "transform 0.2s ease";
                this.index += 500;
            }
        }
    }

}

</script>
<style scoped>
.slider {
    width:500px;
    height:300px;
    margin:100px auto 0;
    overflow: hidden;
    position: relative;
}
.container-slides {
    display:flex;
}
.img-slider {
    width:100%;
    height: auto;
}
.btn {
    outline: none;
    border:none;
    width:50px;
    height:50px;
    border-radius: 50%;
    display:block;
    position:absolute;
    z-index:1000;
    cursor:pointer;
    font-size:20px;
    display: flex;
    justify-content:center;
    align-items:center;
}

.icone {
    width: 15px;
}
.btn-left {
    top:50%;
    transform:translateY(-50%);
    left:5px;
}
.btn-right {
    top:50%;
    transform:translateY(-50%);
    right:5px;
}

</style>