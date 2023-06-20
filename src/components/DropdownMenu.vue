<template>
    <div>
        
        <div class="dropdown menu-button">
                <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                    Dropdown
                </button>
                <ul class="dropdown-menu">
                    <li v-for="selection in dropdownList" @click="$emit('selectionEvent', selection.archetype_name)"><button class="dropdown-item" href="#" type="button">{{ selection.archetype_name }}</button></li>
                </ul>
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
        dropdownList : Array
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