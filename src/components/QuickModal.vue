<template>
  <div class="quickModal" :class="dataToPass">
    <!-- Modal -->
    <div
      class="modal fade"
      :id="id"
      tabindex="-1"
      role="dialog"
      aria-labelledby="modelTitleId"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <slot name="title">Title</slot>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <slot></slot>
            <slot name="body"></slot>
            <h3>{{modalProp}}</h3>
          </div>
          <div class="modal-footer">
            <slot name="footer">Footzone</slot>

            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "quickModal",
  data() {
    return {};
  },
  computed: {},
  methods: {},
  components: {},
  props: ["id", "modalProp", "dataToPass"],
};
</script>


<style scoped>
</style>