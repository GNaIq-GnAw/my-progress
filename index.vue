<template>
    <div class="MyProgress" :style="styles" @click="onClick"></div>
</template>

<script>
    export default {
        name: "MyProgress",
        props: {
            percentage: {
                type: [Number, String],
                default: 0
            },
            color: {
                type: String,
                default: '#4D88FD'
            },
            railColor: {
                type: String,
                default: '#E8E8E8'
            },
            radius: Boolean,
            width: {
                type: Number,
                default: 4
            }
        },
        computed: {
            styles() {
                let n = this.percentage;
                return {
                    borderRadius: this.radius ? '2px' : 0,
                    background: `linear-gradient(90deg, ${this.color} 0%, ${this.color} ${n}%, ${this.railColor} ${n}%, ${this.railColor} 100%)`,
                    height: this.width + 'px'
                }
            }
        },
        methods: {
            onClick(event) {
                window.console.log('event', event.clientX);
            }
        }
    }
</script>

<style lang="scss" scoped>
    .MyProgress {
        //height: 4px;
        background: linear-gradient(90deg, #4D88FD 0%, #4D88FD 80%, #E8E8E8 80%, #E8E8E8 100%);
        //background: #E8E8E8;
        //display: inline-block;
        width: 100%;
    }
</style>
