<template>
  <div class="max-w-xl mx-auto">
    <h1 class="text-2xl text-center font-bold mt-10 mb-4">Invoice Generator</h1>
    <form @submit.prevent="submitInvoice" class="bg-gray-100 rounded-lg p-4">
      <div class="mb-4">
        <label for="clientName" class="block font-medium text-gray-700"
          >Client Name:</label
        >
        <input
          type="text"
          id="clientName"
          v-model="clientName"
          required
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 py-2 px-3"
        />
      </div>
      <div class="mb-4">
        <label for="invoiceAmount" class="block font-medium text-gray-700"
          >Invoice Amount:</label
        >
        <input
          type="number"
          id="invoiceAmount"
          v-model="invoiceAmount"
          required
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 py-2 px-3"
        />
      </div>
      <div class="mb-4">
        <label for="dueDate" class="block font-medium text-gray-700"
          >Due Date:</label
        >
        <input
          type="date"
          id="dueDate"
          v-model="dueDate"
          required
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 py-2 px-3"
        />
      </div>
      <div class="mb-4">
        <label for="otherDetails" class="block font-medium text-gray-700"
          >Other Details:</label
        >
        <textarea
          id="otherDetails"
          v-model="otherDetails"
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 py-2 px-3"
        ></textarea>
      </div>
      <div class="text-center">
        <button
          type="submit"
          class="inline-block bg-indigo-500 hover:bg-indigo-700 text-white font-bold py-2 px-4 rounded"
        >
          Generate Invoice
        </button>
      </div>
    </form>
  </div>
</template>
<script>

export default {
  name: "InvoiceGenerator",
  data() {
    return {
      clientName: "",
      invoiceAmount: 0,
      dueDate: "",
      otherDetails: "",
    };
  },
  methods: {
    submitInvoice() {
      console.log("New Invoice:", {
        clientName: this.clientName,
        invoiceAmount: this.invoiceAmount,
        dueDate: this.dueDate,
        otherDetails: this.otherDetails,
      });
      this.clientName = "";
      this.invoiceAmount = 0;
      this.dueDate = "";
      this.otherDetails = "";
    },
  },
};
</script>
<style>
input {
  height: 40px !important;
  padding-left: 10px !important;
  padding-right: 10px !important;
}

textarea {
  padding: 10px !important;
}

input:focus,
textarea:focus {
  outline: none !important;
  border: solid 1px rgb(59 130 246 / 0.5) !important;
}
</style>
