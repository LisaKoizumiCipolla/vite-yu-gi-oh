<template>
    <div class="menu">
        <div v-for="selection in archetypeList" onclick="$emit(selection.archetype)">
            {{ selection.archetype }}
        </div>
    </div>
</template>
<script>
export default {


    data() {
        return{
        }
    },

    props : {
        archetypeList : Array
    },
}
</script>
<style lang="scss" scoped>
    .menu{
        height: 200px;
        width: 200px;
        background-color: purple;
    }

</style>