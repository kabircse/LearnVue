import ChildForm from './components/ChildForm'

new Vue({
  el: '#app',
  data: {
    item: {},
    bus: new Vue(),
  },
  template: `
  <div>
     <ChildForm :item="item" :bus="bus" ref="form" />
     <button type="submit" @click.prevent="submit">Post</button>
  </div>
  `,
  methods: {
    submit() {
      this.bus.$emit('submit')
    }
  },
  components: { ChildForm },
})

**Code of ChildForm.**

<template>
 ...
</template>

<script>
export default {
  name: 'NowForm',
  props: ['item', 'bus'],
  methods: {
    submit() {
        ...
    }
  },
  mounted() {
    this.bus.$on('submit', this.submit)
  },  
}
</script>
