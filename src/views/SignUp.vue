<template>
  <div class="flex justify-center">
      <h1 class="mt-20 mb-10">Sign Up</h1>
  </div>
  <div class="flex justify-center">
    <div class="w-80 flex flex-col">
      <TextInput
        id="email"
        v-model="email"
        class="w-full mt-4"
        label="Email"
        type="email"
        required
      />
      <TextInput
        id="password"
        v-model="password"
        class="w-full mt-4"
        label="Password"
        type="password"
        required
      />
      <p>Your password needs to have at least eight characters.</p>
      <div class="flex mt-10">
        <LobButton
          variant="secondary"
          @click.prevent="$router.back"
        >
          <svg
            viewBox="0 0 24 24"
            class="w-5 h-5 fill-current"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M12.7071 4.29289C13.0976 4.68342 13.0976 5.31658 12.7071 5.70711L7.41421 11H19C19.5523 11 20 11.4477 20 12C20 12.5523 19.5523 13 19 13H7.41421L12.7071 18.2929C13.0976 18.6834 13.0976 19.3166 12.7071 19.7071C12.3166 20.0976 11.6834 20.0976 11.2929 19.7071L4.29289 12.7071C3.90237 12.3166 3.90237 11.6834 4.29289 11.2929L11.2929 4.29289C11.6834 3.90237 12.3166 3.90237 12.7071 4.29289Z"
            />
          </svg>
        </LobButton>
        <LobButton
          class="ml-4 flex-grow"
          :disabled="buttonDisabled"
          @click.prevent="handleSubmit"
        >
          Sign Up
        </LobButton>
      </div>
    </div>
  </div>
</template>

<script>
// (1)
// button with icon has no text and therefore a screen reader user has no idea what to do with it
// a few options to fix, this is a great blog post: https://www.sarasoueidan.com/blog/accessible-icon-buttons/
// add aria-hidden="true" and focusable="false" on svg, add text on button that's screen reader only

// (2)
// this doesn't work for a screen reader user because the "Your password needs to have at least eight characters." text is never read to them
// there is no indication of what went wrong to the user, and the button is now disabled
// this can be fixed by adding an `aria-describedby` to the password input, and then adding an `id` to the p tag with the same string

export default {
  name: 'sign-up',
  data () {
    return {
      email: '',
      password: '',
      buttonDisabled: false
    }
  },
  methods: {
    handleSubmit () {
      if (this.password.length < 8) {
        this.buttonDisabled = true;
        return;
      }

      alert('information submitted');
    }
  }
}
</script>
