<template>
  <div>
    Hello World!
    {{result}}
  </div>
</template>
<script setup>
 const { result } = useCustomComposable(12,5);

</script>