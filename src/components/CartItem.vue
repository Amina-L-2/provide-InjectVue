<template>
    <li>
        {{ item.name }} - {{ item.price }}€
    </li>
</template>

<script setup>
defineProps({
    item: {
        type: Object,
        required: true
    }
});
</script>

<style scoped>
li {
  padding: 0.6rem 0;
  border-bottom: 1px solid #eee;
}
</style>