<template>
    <div class="month-box">
        <month-header class="header" :propmonth="propmonth"></month-header>
        <month-list></month-list>
        <month-gage></month-gage>
    </div>
</template>

<script>
    import monthHeader from './month/monthHeader'
    import monthList from './month/monthList'
    import monthGage from './month/monthGage'
    export default {
        props: ['propmonth'],
        components: {
            monthHeader,
            monthList,
            monthGage
        }
    }
</script>

<style lang="scss" scoped>
.month-box {
    display: flex;
    justify-content: space-between;
    overflow: hidden;
    position: relative;
    box-sizing: border-box;
    height: 100%;
    padding: 20px;
    .header {
        position: absolute;
        right: 50px;
        bottom: -10px;
        font-weight: 900;
        font-size: 100px;
        color: #e1e1e1;
        opacity: .5;
    }
}
</style>