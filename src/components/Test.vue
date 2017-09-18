<template>
    <div class="test">
        <p>{{ message }}</p>
        <!-- conditions -->
        <p v-if="seen">Seen</p>
        <!-- loops -->
        <ol>
          <li v-for="todo in todos">
            {{ todo.text }}
          </li>
        </ol>
        <!-- user interaction -->
        <p>{{ msgToReverse }}</p>
        <button v-on:click="reverseMessage">Reverse Message</button>
        <!-- two-way binding directive -->
        <p>{{ message }}</p>
        <input v-model="message">       
    </div>
</template>

<script>
export default {
  name: 'test',
  data() {
    return {
      message: 'Hello Vue.js!',
      msgToReverse: 'Hello Vue.js!',
      seen: true,
      todos: [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' },
      ],
    };
  },
  methods: {
    reverseMessage() {
      this.msgToReverse = this.msgToReverse.split('').reverse().join('');
    },
  },
};
</script>
