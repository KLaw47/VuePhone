<script setup>
import ContactListItem from './ContactListItem.vue'

const props = defineProps(['contacts'])
const emit = defineEmits(['remove'])
</script>

<template>
  <div class="panel is-success">
    <div class="panel-heading">Contacts</div>
    <div class="panel-block is-flex is-flex-direction-column is-align-items-stretch">
      <div v-if="props.contacts && props.contacts.length > 0">
        <div v-for="contact in props.contacts" :key="contact.phoneNumber">
          <ContactListItem @remove="emit('remove', contact)" :contact="contact" />
        </div>
      </div>
      <div v-else>
        No contacts found.
      </div>
    </div>
  </div>
</template>

<style scoped></style>

