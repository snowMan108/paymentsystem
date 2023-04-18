<template>
  <div class="container mx-auto py-8">
    <h2 class="text-2xl font-bold text-gray-800 mb-4">Invoice List</h2>
    <div class="w-full overflow-auto">
      <table class="w-full border-collapse bg-white shadow-md rounded">
        <thead>
          <tr
            class="bg-gray-200 text-gray-700 uppercase text-sm leading-normal"
          >
            <th class="py-3 px-6 text-left">Invoice Number</th>
            <th class="py-3 px-6 text-left">Client Name</th>
            <th class="py-3 px-6 text-left">Amount</th>
            <th class="py-3 px-6 text-left">Payment Status</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="invoice in invoices"
            :key="invoice.invoiceNumber"
            class="border-b border-gray-200 hover:bg-gray-100"
          >
            <td class="py-4 px-6">{{ invoice.invoiceNumber }}</td>
            <td class="py-4 px-6">{{ invoice.clientName }}</td>
            <td class="py-4 px-6">{{ invoice.amount }}</td>
            <td class="py-4 px-6">{{ invoice.paymentStatus }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      invoices: [
        {
          invoiceNumber: 123,
          clientName: "John Doe",
          amount: 1000,
          paymentStatus: "Paid",
        },
        {
          invoiceNumber: 124,
          clientName: "Jane Doe",
          amount: 1500,
          paymentStatus: "Unpaid",
        },
        {
          invoiceNumber: 125,
          clientName: "Bob Smith",
          amount: 2000,
          paymentStatus: "Paid",
        },
      ],
    };
  },
};
</script>

<style scoped>
table td {
  vertical-align: top;
}

@media only screen and (max-width: 768px) {
  table td {
    display: block;
  }
  table tr {
    border-bottom: 1px solid #ddd;
    display: block;
    padding: 5px 0;
  }
  table tr:nth-of-type(even) {
    background-color: rgba(0, 0, 0, 0.05);
  }
  table tr:nth-of-type(odd) {
    background-color: #fff;
  }
  table th {
    display: none;
  }
}
</style>
