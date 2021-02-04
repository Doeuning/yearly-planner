<template>
    <div>
        <header>
            2021 Yearly Planner
            <button type="button" class="btn-add" @click="addTodo">추가</button>
        </header>
    </div>
</template>

<script>
    export default {
        methods: {
            addTodo(){
                this.$emit('addTodo');
            }
        }
    }
</script>

<style lang="scss" scoped>
header {
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    text-align: center;
    font-weight: 700;
    font-size: 25px;
    line-height: 50px;
    .btn-add {
        box-shadow: 0px 0px 8px 0px rgba(0, 0, 0, 0.05);
        border: none;
        border-radius: 5px;
        padding: 5px 15px;
        background: cornflowerblue;
        font-weight: 700;
        font-size: 15px;
        color: #fff;
    }
}

</style>