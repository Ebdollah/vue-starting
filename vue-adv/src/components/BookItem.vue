<template lang="">
    <div class="p-8">
        <h1 class="text-sm text-red-500">{{ bookName }}</h1>
        <p class="text-sm text-blue-500">{{ bookDesc }}</p>
        <button @click=itemFav class="bg-blue-600 rounded-lg p-2 m-2">
            Add to Favorite
        </button> 
    </div>
</template>
<script>
export default {
    name: 'BookItem',
    props: ['bookName', 'bookDesc', 'isFavourite'],
    methods:{
        itemFav(){
            this.$emit("item-fav",this.bookName)
        }
    }
    
}
</script>
