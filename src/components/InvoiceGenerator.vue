<template>
  <div class="max-w-xl mx-auto">
    <h1 class="text-2xl text-center font-bold mb-4">Invoice Generator</h1>
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
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
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
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
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
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
        />
      </div>
      <div class="mb-4">
        <label for="otherDetails" class="block font-medium text-gray-700"
          >Other Details:</label
        >
        <textarea
          id="otherDetails"
          v-model="otherDetails"
          class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
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
<!--
  In the above code, CSS classes such as "max-w-xl", "mx-auto", "text-2xl", "font-bold", "mb-4", "bg-gray-100", "rounded-lg", "p-4", "mt-1", "block", "w-full", "rounded-md", "border-gray-300", "shadow-sm", "focus:border-indigo-500", "focus:ring", "focus:ring-indigo-200", "focus:ring-opacity-50", "text-center", "inline-block", "bg-indigo-500", "hover:bg-indigo-700", "text-white", "font-bold", "py-2", "px-4" and "rounded" are added to various HTML elements to make the UI responsive, visually appealing and user-friendly.
  --->
<script>
/*In this example, we created a form with input fields for the client name, invoice amount, due date, and other details. 
We added v-model directives to bind the values of the form fields to our component's data properties. We also added a submit button to generate the invoice.

When the user submits the form, the submitInvoice method is called.
Here, you can add your logic to save the new invoice to the database or perform any other actions required.
In this example, we simply log the new invoice object to the console.

After saving your invoice successfully, reset the form fields to their initial values so the user can generate another invoice.
*/

export default {
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
      // Here you can add your logic to save the new invoice to the database or perform any other actions required
      console.log("New Invoice:", {
        clientName: this.clientName,
        invoiceAmount: this.invoiceAmount,
        dueDate: this.dueDate,
        otherDetails: this.otherDetails,
      });
      // After saving your invoice successfully, reset the form fields to their initial values
      this.clientName = "";
      this.invoiceAmount = 0;
      this.dueDate = "";
      this.otherDetails = "";
    },
  },
};
</script>
