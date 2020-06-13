<template>
    <div class="timer-container">
        <div class="timer-container__creator">
            <input class="timer-container__creator-input" type="text" placeholder="Timer Name" v-model="name" v-on:keyup.enter="createTimer">
            <button class="timer-container__creator-button" v-on:click="createTimer" >Create Timer</button>
        </div>
        <ul v-show="visible" class="timer-container__list">
            <li class="timer-container__list-li" v-for="(item, index) in timers" :key="index">
                <p class="timer-container__list-li-name">{{item.name}}</p>
                <p class="timer-container__list-li-time">{{updateHours(index)}}:{{updateMinutes(index)}}:{{updateSeconds(index)}}</p>
                <button class="timer-container__list-li-pause" v-on:click="stop(index)" v-show="!timers[index].pause">
                    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                        <path fill="#FFFFFF" d="M14,19H18V5H14M6,19H10V5H6V19Z" />
                    </svg>
                </button>
                <button class="timer-container__list-li-start" v-on:click="start(index)" v-show="timers[index].pause">
                    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                        <path fill="#FFFFFF" d="M8,5.14V19.14L19,12.14L8,5.14Z" />
                    </svg>
                </button>
                <button class="timer-container__list-li-delete">
                    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                        <path fill="#FFFFFF" d="M19,4H15.5L14.5,3H9.5L8.5,4H5V6H19M6,19A2,2 0 0,0 8,21H16A2,2 0 0,0 18,19V7H6V19Z" />
                    </svg>
                </button>
            </li>
        </ul>
    </div>
</template>

<script>
import { METHODS } from 'http'
export default {
    name: 'timer',
    data() {
        return {
            timer: '',
            name: '',
            timers: [],
            visible: false,
        }
    },
    methods: {
        createTimer() {
            clearInterval(this.timer)
            this.visible = true;
            this.timers.unshift({
                name: this.name || new Date().toLocaleDateString() + ' ' + new Date().toLocaleTimeString(),
                seconds: 0,
                minutes: 0,
                hours: 0,
                pause: false
            }); 
            console.log(this.timers);
            this.timer = setInterval(() => this.startTimer('work'), 1000);
        },
        startTimer() {
            for (let item of this.timers) {
                if (!item.pause) {
                    item.seconds++;
                    if (item.seconds == 60) {
                        item.minutes++;
                        item.seconds = 0;
                    }
                    if (item.minutes == 60) {
                        item.hours++;
                        item.minutes = 0;
                    }
                }
            }
            
        },
        updateSeconds(index) {
            return (this.timers[index].seconds < 10) ? '0' + this.timers[index].seconds : this.timers[index].seconds;
        },
        updateMinutes(index) {
            return (this.timers[index].minutes < 10) ? '0' + this.timers[index].minutes : this.timers[index].minutes;
        },
        updateHours(index) {
            return (this.timers[index].hours< 10) ? '0' + this.timers[index].hours : this.timers[index].hours;
        },
        stop(index) {
            clearInterval(this.timer)
            this.timer = setInterval(() => this.startTimer(), 1000); 
            this.timers[index].pause = true;
        },
        start(index) {
            clearInterval(this.timer);
            this.timers[index].pause = false;
            this.timer = setInterval(() => this.startTimer(), 1000); 
        }
    }
}
</script>

<style lang="scss" scoped>
    .timer-container {
        max-width: 770px;
        margin: 60px auto 0;
        padding: 40px 0 0;
        background: #FFFFFF;
        box-shadow: 0px 1px 3px rgba(32, 33, 39, 0.12);
        border-radius: 12px;
        &__creator {
            display: flex;
            justify-content: center;
            padding-bottom: 30px;
            &-input {
                width: 305px;
                background: #F8F9FA;
                border: 1px solid #E7E8EA;
                padding: 15px 20px;
                border-radius: 6px;
                font-weight: normal;
                font-size: 17px;
                line-height: 23px;
                color: rgba(103, 108, 117, 0.7);
            }
            &-button {
                width: 165px;
                padding: 13px 0;
                margin-left: 20px;
                background: linear-gradient(163.14deg, #FF8E64 0%, #FFE641 100%);
                border-radius: 6px;
                border: none;
                font-weight: bold;
                font-size: 17px;
                line-height: 24px;
                text-align: center;
                letter-spacing: 1px;
                color: #FFFFFF;
                cursor: pointer;
            }
        }
        &__list {
            border-top: 2px solid #E7E8EA ;
            padding: 10px 10px 20px;
            &-li {
                display: flex;
                padding: 20px;
                &-name {
                    width: 35%;
                    padding-right: 60px;
                    text-align: right;
                    font-weight: 800;
                    font-size: 20px;
                    line-height: 50px;
                    color: #5586F2;
                }
                &-time {
                    width: 18%;
                    background: #E7E8EA;
                    border: 1px solid #E7E8EA;
                    box-sizing: border-box;
                    border-radius: 6px;
                    font-weight: normal;
                    font-size: 17px;
                    line-height: 50px;
                    color: #676C75;
                    text-align: center;
                }
                &-pause {
                    width: 50px;
                    height: 50px;
                    margin-left: 6%;
                    margin-right: 10px;
                    background: linear-gradient(135deg, #7956EC 0%, #2FB9F8 100%);
                    border-radius: 25px;
                    border: none;
                    display: flex;
                    cursor: pointer;
                    svg {
                        margin: auto;
                    }

                }
                &-start {
                    width: 50px;
                    height: 50px;
                    margin-left: 6%;
                    margin-right: 10px;
                    background: linear-gradient(135deg, #009FC5 0%, #3CECB0 100%);
                    border-radius: 25px;
                    border: none;
                    display: flex;
                    cursor: pointer;
                    svg {
                        margin: auto;
                    }

                }
                &-delete {
                    width: 50px;
                    height: 50px;
                    margin-left: 10px;
                    background: linear-gradient(135deg, #F23673 0%, #FCA069 100%);
                    border-radius: 6px;
                    border: none;
                    display: flex;
                    cursor: pointer;
                    svg {
                        margin: auto;
                    }
                }
            }
        }
    }
</style>