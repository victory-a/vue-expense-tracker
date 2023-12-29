<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      v-bind:key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>${{ transaction.amount }}</span
      ><button class="delete-btn">x</button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from 'vue'
defineProps({
  transactions: {
    type: Array,
    required: true
  }
})
</script>

<!-- composition api v3 -->
<!-- <script setup>
const transactions = [
  { id: 1, text: 'Flower', amount: -19.99 },
  { id: 2, text: 'Salary', amount: 299.97 },
  { id: 3, text: 'Book', amount: -10 },
  { id: 4, text: 'Camera', amount: 150 }
]
</script> -->

<!-- composition api -->
<!-- <script>
export default {
  setup() {
    const transactions = [
      { id: 1, text: 'Flower', amount: -19.99 },
      { id: 2, text: 'Salary', amount: 299.97 },
      { id: 3, text: 'Book', amount: -10 },
      { id: 4, text: 'Camera', amount: 150 }
    ]

    return { transactions }
  }
}
</script> -->

<!-- options api
<script>
// export default {
//   data() {
//     return {
//       transactions: [
//         { id: 1, text: 'Flower', amount: -19.99 },
//         { id: 2, text: 'Salary', amount: 299.97 },
//         { id: 3, text: 'Book', amount: -10 },
//         { id: 4, text: 'Camera', amount: 150 }
//       ]
//     }
//   }
// }
</script> -->
