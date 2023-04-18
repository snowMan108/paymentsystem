<template>
  <div class="max-w-lg mx-auto mt-8">
    <h1 class="text-3xl text-center font-bold mb-8">
      Payment Confirmation Form
    </h1>
    <form
      @submit.prevent="submitPayment"
      class="bg-white rounded-lg shadow-md p-6"
    >
      <div class="mb-4">
        <label for="clientName" class="block text-gray-700 font-medium mb-2"
          >Client Name:</label
        >
        <input
          type="text"
          id="clientName"
          v-model="clientName"
          required
          class="border-2 border-gray-400 rounded-md w-full py-2 px-3 focus:outline-none focus:border-indigo-500"
        />
      </div>
      <div class="mb-4">
        <label for="invoiceNumber" class="block text-gray-700 font-medium mb-2"
          >Invoice Number:</label
        >
        <input
          type="text"
          id="invoiceNumber"
          v-model="invoiceNumber"
          required
          class="border-2 border-gray-400 rounded-md w-full py-2 px-3 focus:outline-none focus:border-indigo-500"
        />
      </div>
      <div class="mb-4">
        <label for="paymentAmount" class="block text-gray-700 font-medium mb-2"
          >Payment Amount:</label
        >
        <input
          type="number"
          id="paymentAmount"
          v-model="paymentAmount"
          required
          class="border-2 border-gray-400 rounded-md w-full py-2 px-3 focus:outline-none focus:border-indigo-500"
        />
      </div>
      <div class="mb-4">
        <label for="txLink" class="block text-gray-700 font-medium mb-2"
          >Transaction Link:</label
        >
        <input
          type="text"
          id="txLink"
          v-model="txLink"
          required
          class="border-2 border-gray-400 rounded-md w-full py-2 px-3 focus:outline-none focus:border-indigo-500"
        />
      </div>
      <div class="mt-6 text-center">
        <button
          type="submit"
          class="bg-indigo-500 hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded-full"
        >
          Confirm Payment
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "PaymentConfirmation",
  data() {
    return {
      clientName: "",
      invoiceNumber: "",
      paymentAmount: 0,
      txLink: "",
    };
  },
  methods: {
    submitPayment() {
      console.log("Payment Confirmed:", {
        clientName: this.clientName,
        invoiceNumber: this.invoiceNumber,
        paymentAmount: this.paymentAmount,
        txLink: this.txLink,
      });
      this.clientName = "";
      this.invoiceNumber = "";
      this.paymentAmount = 0;
      this.txLink = "";
    },
  },
};
</script>
