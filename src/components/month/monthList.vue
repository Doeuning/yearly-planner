<template>
    <div>
        <ul>
            <li v-for="(item, index) in propmonth" :key="index" :class="{checked: checked}">
                <label>
                    <input type="checkbox" :checked="checked" :value="item">
                    <span>{{ item }}</span>
                </label>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                checked: false
            }
        },
        props: ['propmonth'],
    }
</script>

<style lang="scss" scoped>
ul {
    li {
        border-radius: 5px;
        padding: 5px;
        background: #efefef;
        transition: all .3s ease-in;
        & + li {
            margin: 10px 0 0;
        }
        &.checked {
            background: cornflowerblue;
            color: #fff;
        }
        label {
            position: relative;
            input {
                position: absolute;
                top: 0;
                right: 0;
                bottom: 0;
                left: 0;
                z-index: 1;
                opacity: 0;
            }
        }
    }
}
</style>