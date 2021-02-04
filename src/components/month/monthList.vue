<template>
    <div>
        <ul>
            <li v-for="month in propmonth" :key="month.id">
                <label>
                    <input type="checkbox">
                    <span>{{ month.todoList }}</span>
                </label>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['propmonth'],
        
    }
</script>

<style lang="scss" scoped>
ul {
    li {
        border-radius: 5px;
        padding: 5px;
        background: #efefef;
        & + li {
            margin: 10px 0 0;
        }
    }
}
</style>