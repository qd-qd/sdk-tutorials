<template lang="pug">
    .form-wrapper
      form
        input(v-model="name" name='fields[name]' id="name" placeholder="Name" type="text" required='required' class="tm-rf0 tm-lh-copy tm-title")
        input(v-model="email" name='fields[email]' id="email" placeholder="Email" type="email" required='required' class="tm-rf0 tm-lh-copy tm-title")
        button(class="tm-button" @click.prevent='submitForm') Signup
        label.tm-lh-title.tm-rf-1.tm-medium.tm-muted(v-if="message") {{message}}
        
</template>

<script>
    import validateEmail from 'email-validator';
    import querystring from 'querystring';

    export default {
        data() {
          return {
            email: null,
            name: null,
            message: null,
            requestUrl: this.formId?.includes('https://') ? this.formId : "https://static.mailerlite.com/webforms/submit/" + this.formId
          }
        },
        props: ['formId'],
        methods: {
          async submitForm(event) {
            event.preventDefault();
            
            // check email
            if (!validateEmail.validate(this.email)) {
              this.message = "Email not valid";
              return;
            }

            // check required fields
            if (!this.name || this.name === "") {
              this.message = "Missing required field name";
              return;
            }

            // fetch subscription api
            const options = {
              method: 'POST',
              mode: 'no-cors',
              headers: {
                'Content-Type': 'application/x-www-form-urlencoded',
              },
              body: querystring.stringify({
                'fields[email]': this.email,
                'fields[name]': this.name,
                'ml-submit': 1,
                'anticsrf': true
              }),
            }

            try {
              await fetch(this.requestUrl, options);
            } catch (error) {
              console.error(error);
              this.message = "An error occurred. Please try again later";
              return;
            }

            this.message = "Thank you, we have received your submission"
          }
        }
    }
</script>

<style lang="stylus" scoped>
  form
    display flex
    flex-direction column
    justify-content center
    
    input
      outline none
      width 100%
      height 3rem
      border none
      border-radius .5rem
      padding var(--spacing-3) 4rem var(--spacing-3) var(--spacing-5)
      transition color 0.15s ease-out, background 0.15s ease-out
      background var(--background-color-secondary)
      margin-bottom 16px
      &::placeholder
        color var(--semi-transparent-color-2)
        transition color 0.15s ease-out
      &:hover
        &:not(:focus)::placeholder
          color var(--semi-transparent-color-3)

    button
      width fit-content
      margin auto
      margin-top 16px

    label
      margin-top 16px
      text-align center
</style>
