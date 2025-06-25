<script setup >
import { onMounted, ref } from 'vue'
import Howtop from './Howtop.vue';
import howtopmob from './howtopmob.vue';
</script>

<template>
    <div class="pk">
    <Howtop/>
</div>

<div class="mob">
    <howtopmob/>
</div>

</template>


<style scoped>

.mob{
    display: none;
}

@media (max-width: 768px) { 
.pk {
    display: none;
}
.mob{
    display: block;
}
}

</style>

