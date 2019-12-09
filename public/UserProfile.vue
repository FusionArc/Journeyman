const users = db.collection('users')

export default {
  props: ['id'],
  data() {
    return {
      user: null,
    }
  },

  watch: {
    id: {
      // call it upon creation too
      immediate: true,
      handler(id) {
        this.$bind('user', users.doc(id))
      },
    },
  },
}