<template>
  <!---The invoice list will display all of the generated invoices for the user. It should include columns for the invoice number, client name, amount, and payment status.-->
  <div>
    <h1>Invoice List</h1>
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
          <td>{{ invoice.id }}</td>
          <td>{{ invoice.clientName }}</td>
          <td>{{ invoice.amount }}</td>
          <td>{{ invoice.status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
/*
In this example, we created a table with columns for the invoice number, client name, amount, and payment status. We used a  v-for  directive to iterate through the  invoices  array and display each invoice's details in a row of the table. 
  
Of course, in a real application, you would get the invoices data from a server API or database instead of hardcoding them as we did here. You would also need to add functionality for checking if a client paid, avoiding double payments, and payments from the past, but this example should give you an idea of how to display your invoices list on the frontend using Vue.js.
*/
export default {
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
