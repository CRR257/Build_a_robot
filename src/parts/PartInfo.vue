<template>
  <div>
    <h1>{{ part.title }}</h1>
    <div>
      {{ part.description }}
    </div>
  </div>
</template>

<script>
import parts from '../data/parts';

export default {
  name: 'PartInfo',
  computed: {
    part() {
    //   const partType = this.$route.params.partType;
    //   const id = this.$route.params.id;
      const { partType, id } = this.$route.params;
      return parts[partType].find(part => part.id === +id);
      // convert the id to a number to compare to part.id
    },
  },
};
</script>
