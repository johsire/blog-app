
<template>
 <div>
   <p>Author: {{this.postObj.name}}</p>
   <p>{{this.postObj.post }}</p>
   <hr>
 </div>
</template>

<script>
export default {
  props: ['postObj']
};
</script>
