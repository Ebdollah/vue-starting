<template>
  <h1 class="text-3xl font-bold underline">
    {{ msg }} 
  </h1>
</template>
<script>
export default{
  name: 'HelloWorld',
  props: {
  msg: String
}
}
</script>