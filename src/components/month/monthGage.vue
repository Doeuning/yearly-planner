<template>
    <div>
        <div class="gage">
            <div class="bar"></div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.gage {
    position: relative;
    width: 10px;
    height: 100%;
    border-radius: 5px;
    background: #efefef;
    .bar {
        position: absolute;
        bottom: 0;
        right: 0;
        left: 0;
        height: 20px;
        background: cornflowerblue;
        width: 10px;
        border-radius: 5px;
    }
}
</style>