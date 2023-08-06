<template>
    <div :class="element.isFinish?'active': ''" class="fieldgroup">
        <label class="marque" for="one">{{element.task}}  </label>
        <input type="checkbox" id="one" v-bind:checked="element.isFinish" v-model="element.isFinish">
        <Staricon @click="markAsImportant(element)"  :is_important="element.is_important"/>
    </div>
    <button @click="removeTask">Supprimer</button>
</template>

<script lang="ts" setup>
/*     const props = defineProps(['element']) */

    const emits = defineEmits(['delete'])
    const props = defineProps<{element: {}}>()
    function markAsImportant(element){
    element.is_important = !element.is_important
    }
    function removeTask(){
    
    emits('delete', props.element)
}

</script>
<style scoped>
    button{
        background: none;
        border: none;
        background-color: red;
        border: 1px solid red;
        color: #fff;
        padding: 0.25rem 0.5rem;
        font-size: 1rem;
        font-weight: 500;
        margin: 0 0 0 0.5rem;
        cursor: pointer;
    }
</style>