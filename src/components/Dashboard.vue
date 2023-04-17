<template>
  <div>
    <h1>Invoice Dashboard</h1>
    <div class="chart-container">
      <!--  1. Dashboard: The dashboard will allow users to see a summary of invoices generated and their payment status. It should display key information such as the total amount of paid and unpaid invoices, along with graphs or charts for an easy overview. -->
    </div>
    <div class="summary-container">
      <div class="total-container">
        <div class="paid-container">
          <h3>Paid Invoices</h3>
          <p>{{ paidCount }} Invoices</p>
          <p>Total Amount: {{ paidTotal }}</p>
        </div>
        <div class="unpaid-container">
          <h3>Unpaid Invoices</h3>
          <p>{{ unpaidCount }} Invoices</p>
          <p>Total Amount: {{ unpaidTotal }}</p>
        </div>
      </div>
      <table>
        <thead>
          <tr>
            <th>Invoice Number</th>
            <th>Client Name</th>
            <th>Amount</th>
            <th>Payment Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="invoice in invoices" :key="invoice.id">
            <td>{{ invoice.invoice_number }}</td>
            <td>{{ invoice.client_name }}</td>
            <td>{{ invoice.amount }}</td>
            <td>{{ invoice.payment_status }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
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
