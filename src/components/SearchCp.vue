<template>
    <div class="search-wrapper py-4">
        <input @input="changeQuery" type="search" name="query" class="form-control form-control-lg search-input">
        <i @click="onReset" class="bt-close "></i>
    </div>
</template>

<script>
export default {
    name: "Search",
    data(){
        return {
            query: ""
        }
    },
    methods : {
        changeQuery(e){ //검색어 입력에 대한 값을 전송하는 부분
            console.log(e);
            console.log(e.target.value);
            this.query = e.target.value;
            this.$emit("@change", this.query);
        }
    }
}
</script>