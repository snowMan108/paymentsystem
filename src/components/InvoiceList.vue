<template>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="mt-8">
      <h1 class="text-3xl font-bold mb-4">Invoice Generator</h1>
      <form
        @submit.prevent="submitInvoice"
        class="bg-white overflow-hidden shadow rounded-lg"
      >
        <div class="px-4 py-5 sm:p-6">
          <div class="grid grid-cols-6 gap-6">
            <div class="col-span-6 sm:col-span-3">
              <label
                for="clientName"
                class="block text-sm font-medium text-gray-700 mb-2"
                >Client Name:</label
              >
              <input
                type="text"
                id="clientName"
                v-model="clientName"
                required
                class="border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 block w-full sm:text-sm border-2"
              />
            </div>

            <div class="col-span-6 sm:col-span-3">
              <label
                for="invoiceAmount"
                class="block text-sm font-medium text-gray-700 mb-2"
                >Invoice Amount:</label
              >
              <input
                type="number"
                id="invoiceAmount"
                v-model="invoiceAmount"
                required
                class="border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 block w-full sm:text-sm border-2"
              />
            </div>

            <div class="col-span-6 sm:col-span-3">
              <label
                for="dueDate"
                class="block text-sm font-medium text-gray-700 mb-2"
                >Due Date:</label
              >
              <input
                type="date"
                id="dueDate"
                v-model="dueDate"
                required
                class="border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 block w-full sm:text-sm border-2"
              />
            </div>

            <div class="col-span-6 sm:col-span-3">
              <label
                for="otherDetails"
                class="block text-sm font-medium text-gray-700 mb-2"
                >Other Details:</label
              >
              <textarea
                id="otherDetails"
                v-model="otherDetails"
                class="border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 block w-full sm:text-sm border-2"
              ></textarea>
            </div>
          </div>
        </div>
        <div class="px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
          <button
            type="submit"
            class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-4 py-2 bg-indigo-600 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 sm:ml-3 sm:w-auto sm:text-sm"
          >
            Generate Invoice
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
<!--
  In this modified code, Tailwindcss classes are added to various HTML elements to make them responsive. For example: 
 
-  max-w-7xl  limits the width of the container to 7xl (max width of 80rem) 
 
-  mx-auto  centers the container horizontally 
 
-  px-4 sm:px-6 lg:px-8  sets the padding of the container to 4 on small screens, 6 on medium screens, and 8 on large screens 
 
-  sm:col-span-3  sets the number of columns an element spans on small screens to 3 
 
-  sm:w-auto  sets the width of an element to auto on small screens 
 
-  sm:text-sm  sets the font size of an element to sm on small screens 
 
-  sm:flex sm:flex-row-reverse  changes the layout of the form buttons to a row on small screens and reverses the order of the buttons 
 
-  sm:ml-3  adds a left margin of 3 to the second form button on small screens 
 
By using Tailwindcss classes like these, you can quickly create a responsive and visually appealing UI.
-->
<script>
/*
In this example, we created a table with columns for the invoice number, client name, amount, and payment status. We used a  v-for  directive to iterate through the  invoices  array and display each invoice's details in a row of the table. 
  
Of course, in a real application, you would get the invoices data from a server API or database instead of hardcoding them as we did here. You would also need to add functionality for checking if a client paid, avoiding double payments, and payments from the past, but this example should give you an idea of how to display your invoices list on the frontend using Vue.js.
*/
export default {
  name: "InvoiceList",
  data() {
    return {
      invoices: [
        { id: 1, clientName: "Client A", amount: 100, status: "Paid" },
        { id: 2, clientName: "Client B", amount: 200, status: "Pending" },
        { id: 3, clientName: "Client C", amount: 300, status: "Paid" },
      ],
    };
  },
};
</script>
