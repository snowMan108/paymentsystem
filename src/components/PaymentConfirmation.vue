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
<!--
In the modified code, CSS classes such as "max-w-lg", "mx-auto", "mt-8", "text-3xl", "font-bold", "mb-8", "bg-white", "rounded-lg", "shadow-md", "p-6", "text-gray-700", "font-medium", "mb-2", "border-2", "rounded-md", "w-full", "py-2", "px-3", "focus:outline-none", "focus:border-indigo-500", "mt-6", "text-center", "bg-indigo-500", "hover:bg-indigo-700", "text-white", "font-bold" and "rounded-full" are added to various HTML elements to make the UI responsive, visually appealing and user-friendly.

-->
<script>
/*
In this example, we created a form with input fields for the client name, invoice number, payment amount, and transaction link. We added  v-model  directives to bind the values of the form fields to our component's data properties. We also added a submit button to confirm the payment. 
 When the client submits the form, the  submitPayment  method is called. Here, you can add your logic to confirm the payment and update the invoice data accordingly. In this example, we simply log the payment confirmation object to the console. 
 After confirming the payment successfully, reset the form fields to their initial values so the client can confirm another payment.
*/
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
      // Here you can add your logic to confirm the payment and update the invoice data accordingly
      console.log("Payment Confirmed:", {
        clientName: this.clientName,
        invoiceNumber: this.invoiceNumber,
        paymentAmount: this.paymentAmount,
        txLink: this.txLink,
      });
      // After confirming the payment, reset the form fields to their initial values
      this.clientName = "";
      this.invoiceNumber = "";
      this.paymentAmount = 0;
      this.txLink = "";
    },
  },
};
</script>
