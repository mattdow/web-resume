<template>
  <ul>
    <li 
      contenteditable="true" 
      @input="TODO"
    >
      {{ contactInfo.phone }}
    </li>
    <li 
      contenteditable="true" 
      @input="updateNestedProperty($event, 'contactInfo', 'email')"
    >
      {{ contactInfo.email }}
    </li>
    <li 
      contenteditable="true" 
      @input="updateNestedProperty($event, 'contactInfo', 'address')"
    >
      {{ contactInfo.address }}
    </li>
  </ul>
</template>

<script>
  export default {
    props: ["contactInfo"]
  }
</script>