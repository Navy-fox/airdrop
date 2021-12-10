<script>
export default {
  name: "modal-mixin",
  methods: {
    CloseModal() {
      // v-model это emit(input(ввод) / change) и значение :value
      this.$emit("input", false);
    },
  },
};
</script>
