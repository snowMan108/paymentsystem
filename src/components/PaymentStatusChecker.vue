<template>
  <div class="max-w-md mx-auto">
    <h1 class="text-3xl font-bold text-center mb-6 mt-10">
      Payment Status Checker
    </h1>
    <form
      class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4"
      @submit.prevent="checkPayment"
    >
      <div class="mb-4">
        <label class="block text-gray-700 font-bold mb-2" for="txLink"
          >Transaction Link</label
        >
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="txLink"
          type="text"
          v-model="txLink"
          required
        />
      </div>
      <div class="flex items-center justify-between">
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="submit"
        >
          Check Payment Status
        </button>
      </div>
    </form>
    <div class="text-center" v-if="paymentStatus !== null">
      <h2 class="text-2xl font-bold" v-if="paymentStatus">
        Payment Status: <span class="text-green-500">Paid</span>
      </h2>
      <h2 class="text-2xl font-bold" v-else>
        Payment Status: <span class="text-red-500">Unpaid</span>
      </h2>
    </div>
  </div>
</template>
<script>
export default {
  name: "PaymentStatusChecker",
  data() {
    return {
      txLink: "",
      paymentStatus: null,
    };
  },
  methods: {
    checkPayment() {
      this.paymentStatus = Math.random() >= 0.5;
    },
  },
};
</script>
