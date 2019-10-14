<template>
    <div class="card">
        <div class="card-header">
            Dynamic Styling
        </div>
        <div class="card-body">
            <p class="my-0">Width</p>
            <input class="form-control mb-3" type="number" v-model="width" >
            <p class="my-0">Height</p>
            <input class="form-control mb-3" type="number" v-model="height" >
            <p class="my-0">Border</p>
            <input class="form-control mb-3" type="number" v-model="border" >
            <p class="my-0">Color</p>
            <select class="form-control mb-3" v-on:change="changeBgColor" id="bgcolorselect">
                <option v-for="item in colors" v-bind:key="item.id" :value="item">{{item}}</option>
            </select>
            <div :style="myStyles"></div>
        </div>
    </div>
</template>

<script>
    export default {
        data: function(){
            return {
                colors: ['red','blue','green','black'],
                bgColor: 'red',
                width: '200',
                height: '200',
                border: '0',
            }
        },
        computed:{
            myStyles : function (){
                return {
                    backgroundColor: this.bgColor,
                    width: this.width + "px",
                    height: this.height + "px",
                    borderRadius : this.border + "px"
                }
            }
        },
        methods:{
            changeBgColor : function(){
                // this.bgColor = document.getElementById('bgcolorselect').value;
                this.bgColor = event.target.value;
            }
        }
    }
</script>
