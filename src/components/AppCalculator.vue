<template>
  <div>
    <input
      type="number"
      v-model="number1"
      placeholder="Enter first number"
    />
    <input
      type="number"
      v-model="number2"
      placeholder="Enter second number"
    />
   
    <!-- Render the select field only if both numbers are inputted -->
    <select v-if="canCalculate" v-model="selectedOperator">
      <option value="*">Multiply</option>
      <option value="/">Divide</option>
      <option value="+">Add</option>
      <option value="-">Subtract</option>
    </select>
   
    <!-- Display the result if calculation is possible -->
    <p v-if="result !== null">Result: {{ result }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed, ref } from 'vue';

export default defineComponent({
  name: 'AppCalculator',
 
  setup() {
    // Define reactive properties using ref
    const number1 = ref<number | null>(null);
    const number2 = ref<number | null>(null);
    const selectedOperator = ref<string | null>(null);

    // Computed property to check if both numbers are inputted
    const canCalculate = computed(() => {
      return number1.value !== null && number2.value !== null;
    });

    // Computed property to calculate the result based on the selected operator
    const result = computed(() => {
      if (!canCalculate.value || !selectedOperator.value) return null;
     
      switch (selectedOperator.value) {
        case '*':
          return (number1.value as number) * (number2.value as number);
        case '/':
          return (number1.value as number) / (number2.value as number);
        case '+':
          return (number1.value as number) + (number2.value as number);
        case '-':
          return (number1.value as number) - (number2.value as number);
        default:
          return null;
      }
    });

    return {
      number1,
      number2,
      selectedOperator,
      canCalculate,
      result,
    };
  },
});
</script>

<style scoped>
	p{
		color: #2baaff;
		font-size: 25px;
	}
</style>