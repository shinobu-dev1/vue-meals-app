<template>
  <header class="bg-white shadow h-16 flex justify-between items-stretch">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full px-5 text-orange-500 font-bold"
    >
      Home
    </router-link>
    <div class="flex items-center gap-1">
      <div>
        <!-- your content here -->
        <button @click="openModal">Open Modal</button>
        <modal v-if="showModal" :users="users" @close="closeModal"></modal>
      </div>
      <router-link
        :to="{ name: 'byName' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-orange-500 hover:text-white"
      >
        Search Meals
      </router-link>
      <router-link
        :to="{ name: 'byLetter' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-orange-500 hover:text-white"
      >
        Meals By Letter
      </router-link>
      <router-link
        :to="{ name: 'ingredients' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-orange-500 hover:text-white"
      >
        Meals By Ingredients
      </router-link>
    </div>
  </header>
</template>

<script>
import Modal from '../components/Modal.vue';

export default {
  name: 'Nabar',
  components: {
    Modal,
  },
  data() {
    return {
      showModal: false,
      users: [
        { name: 'John', age: 30, email: 'john@example.com' },
        { name: 'Mary', age: 25, email: 'mary@example.com' },
        { name: 'Bob', age: 40, email: 'bob@example.com' },
      ],
    };
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
  },
};
</script>
