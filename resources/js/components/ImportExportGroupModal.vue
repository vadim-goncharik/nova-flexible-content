<template>
    <Modal :show="true">
    <form
      class="mx-auto bg-white dark:bg-gray-800 rounded-lg shadow-lg overflow-hidden"
    >
      <slot>
        <ModalHeader v-text="title" />
        <ModalContent>
            <div class="flex">
                <p class="leading-normal font-bold" v-if="name">
                    {{ name }} 
                </p>
                &nbsp;
                <p class="leading-normal" v-if="message">
                    {{ message }}
                </p>
            </div>
        </ModalContent>
      </slot>

      <ModalFooter>
        <div class="ml-auto">
          <link-button
            type="button"
            dusk="confirm-button"
            @click.prevent="this.$emit('close')"
          >
            {{ ok }}
          </link-button>
        </div>
      </ModalFooter>
    </form>
    </Modal>
</template>

<script>
export default {
    props: ['message', 'ok', 'name', 'title'],

    emits: ['close'],
}
</script>
