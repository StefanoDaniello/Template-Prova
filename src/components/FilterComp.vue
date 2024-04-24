<template>
    <div class="d-flex justify-content-between">
        <h1>Filter-Workshop</h1>
        <select @change="$emit('filter', $event.target.value)">
            <option select value="">all</option>
            <option value="fire">fire</option>
            <option value="summer">summer</option>
        </select>
    </div>
</template>

<script>
    export default {
        name: 'FilterComp',
    }
</script>

<style lang="scss" scoped>

</style>