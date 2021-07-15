import ChildForm from './components/ChildForm'

new Vue({
  el: '#app',
  data: {
    item: {}
  },
  template: `
  <div>
     <ChildForm :item="item" ref="form" />
     <button type="submit" @click.prevent="submit">Post</button>
  </div>
  `,
  methods: {
    submit() {
      this.$refs.form.submit()
    }
  },
  components: { ChildForm },
})

Code of ChildForm.

<template>
 ...
</template>

<script>
export default {
  name: 'NowForm',
  props: ['item'],
  methods: {
    submit() {
        ...
    }
  }
}
</script>
