<template>
    <div class="timer-container">
        <div class="timer-container__creator">
            <input class="timer-container__creator-input" type="text" placeholder="Timer Name" v-model="name">
            <button class="timer-container__creator-button" v-on:click="createTimer">Create Timer</button>
        </div>
        <ul v-show="visible" class="timer-container__list">
            <li class="timer-container__list-li" v-for="(item, index) in timers" :key="index">
                <p class="timer-container__list-li-name">{{item.name}}</p>
                <p class="timer-container__list-li-time">00:00:00</p>
                <button class="timer-container__list-li-pause">
                    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                        <path fill="#FFFFFF" d="M14,19H18V5H14M6,19H10V5H6V19Z" />
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
            name: '',
            timers: [],
            visible: false
        }
    },
    methods: {
        createTimer() {
            this.visible = true;
            // console.log(this.name);
            // let date = new Date() + '';
            // date.slice(0, 24);
            this.timers.unshift({
                name: this.name || date
            })
            console.log(this.timers)

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