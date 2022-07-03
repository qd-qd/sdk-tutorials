<template lang="pug">
    .form-wrapper
        .ml-form-embed(:data-form="formId" :data-account="accountId")
</template>

<script>
    export default {
        props: ['formId', 'accountId']
    }
</script>

<style lang="stylus" scoped>
    input
      outline none
      width 100%
      height 3rem
      border none
      border-radius .5rem
      padding var(--spacing-3) 4rem var(--spacing-3) var(--spacing-5)
      transition color 0.15s ease-out, background 0.15s ease-out
      background var(--background-color-secondary)
      &::placeholder
        color var(--semi-transparent-color-2)
        transition color 0.15s ease-out
      &:hover
        &:not(:focus)::placeholder
          color var(--semi-transparent-color-3)
</style>
