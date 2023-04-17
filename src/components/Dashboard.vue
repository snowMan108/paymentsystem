<template>
  <div class="p-4 md:p-8">
    <!-- Add padding of 4 on small screens and 8 on medium and larger screens -->
    <h1 class="text-2xl md:text-4xl font-bold mb-4">Invoice Dashboard</h1>
    <!-- Increase font size on larger screens and add margin bottom of 4 -->
    <div class="chart-container bg-white shadow-md rounded-lg p-4 mb-4 md:mb-8">
      <!-- Add background color, shadow, rounded corners, padding and margin bottom -->
      <p class="text-center">Insert chart here</p>
      <!-- Center the text -->
    </div>
    <div class="summary-container grid grid-cols-1 md:grid-cols-2 gap-4 mb-8">
      <!-- Use grid to display the summary side by side on medium and larger screens -->
      <div class="total-container bg-white shadow-md rounded-lg p-4">
        <div class="paid-container">
          <h3 class="text-xl font-bold mb-2">Paid Invoices</h3>
          <!-- Increase font size and add margin bottom -->
          <p class="mb-1">{{ paidCount }} Invoices</p>
          <p class="font-bold text-lg mb-2">Total Amount: {{ paidTotal }}</p>
          <!-- Increase font size and make the amount bold -->
        </div>
      </div>
      <div class="total-container bg-white shadow-md rounded-lg p-4">
        <div class="unpaid-container">
          <h3 class="text-xl font-bold mb-2">Unpaid Invoices</h3>
          <p class="mb-1">{{ unpaidCount }} Invoices</p>
          <p class="font-bold text-lg mb-2">Total Amount: {{ unpaidTotal }}</p>
        </div>
      </div>
      <!-- Use the same style for the two containers -->
    </div>
    <table class="w-full table-auto">
      <!-- Use tailwind's table classes to make the table responsive -->
      <thead>
        <tr>
          <th class="px-4 py-2">Invoice Number</th>
          <th class="px-4 py-2">Client Name</th>
          <th class="px-4 py-2">Amount</th>
          <th class="px-4 py-2">Payment Status</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="invoice in invoices" :key="invoice.id">
          <td class="border px-4 py-2">{{ invoice.invoice_number }}</td>
          <td class="border px-4 py-2">{{ invoice.client_name }}</td>
          <td class="border px-4 py-2">{{ invoice.amount }}</td>
          <td class="border px-4 py-2">{{ invoice.payment_status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<!-- You can also add custom tailwind classes in the style section -->
<!-- By using tailwind css classes, you can easily create a beautiful and responsive UI without having to write custom CSS. You can adjust the classes based on your design requirements. --->
<!-- Define a custom height for the chart container -->
<style>
.chart-container {
  height: 300px;
}
</style>

<script>
//In this example, we use a table to display the summary of generated invoices and their payment status. Additionally, we added a summary section that displays the total amount of paid and unpaid invoices, along with the counts of paid and unpaid invoices. The data for invoices is hardcoded in the component, but in a real-world scenario, it should be fetched from a backend API. The chart or graph component can be added by replacing the  div  with the  chart-container  class.

export default {
  data() {
    return {
      invoices: [
        {
          id: 1,
          invoice_number: "INV001",
          client_name: "John Smith",
          amount: 100,
          payment_status: "Paid",
        },
        {
          id: 2,
          invoice_number: "INV002",
          client_name: "Jane Doe",
          amount: 200,
          payment_status: "Pending",
        },
        {
          id: 3,
          invoice_number: "INV003",
          client_name: "Bob Johnson",
          amount: 300,
          payment_status: "Unpaid",
        },
      ],
    };
  },
  computed: {
    // Calculate the total amount of paid invoices
    paidTotal() {
      return this.invoices
        .filter((invoice) => invoice.payment_status === "Paid")
        .reduce((a, b) => a + b.amount, 0);
    },
    // Calculate the total amount of unpaid invoices
    unpaidTotal() {
      return this.invoices
        .filter((invoice) => invoice.payment_status === "Unpaid")
        .reduce((a, b) => a + b.amount, 0);
    },
    // Count the number of paid invoices
    paidCount() {
      return this.invoices.filter(
        (invoice) => invoice.payment_status === "Paid"
      ).length;
    },
    // Count the number of unpaid invoices
    unpaidCount() {
      return this.invoices.filter(
        (invoice) => invoice.payment_status === "Unpaid"
      ).length;
    },
  },
};
</script>
