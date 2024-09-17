<template>
  <h4 
    class="section-headline" 
    contenteditable="true" 
  >
      {{ headline }}
  </h4>
</template>

<script>
    export default {
        props: ["headline"]
	}
</script>