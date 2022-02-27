<template>
    <ul class="row searchResult py-4">
        <List
        
        >
    </ul>
</template>

<script>
import List from "./ListCp.vue";

export default {
    name: "ListWrap",
    components: {List},
    props: ["lists"],
    
}
</script>