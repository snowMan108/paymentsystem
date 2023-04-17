<template>
  <!--Payment Confirmation Form: The payment confirmation form will allow clients to confirm that they have made a payment. It should include fields for the client name, invoice number, payment amount, and transaction link. --->
  <div>
    <h1>Payment Confirmation Form</h1>
    <form @submit.prevent="submitPayment">
      <div class="form-group">
        <label for="clientName">Client Name:</label>
        <input type="text" id="clientName" v-model="clientName" required />
      </div>
      <div class="form-group">
        <label for="invoiceNumber">Invoice Number:</label>
        <input
          type="text"
          id="invoiceNumber"
          v-model="invoiceNumber"
          required
        />
      </div>
      <div class="form-group">
        <label for="paymentAmount">Payment Amount:</label>
        <input
          type="number"
          id="paymentAmount"
          v-model="paymentAmount"
          required
        />
      </div>
      <div class="form-group">
        <label for="txLink">Transaction Link:</label>
        <input type="text" id="txLink" v-model="txLink" required />
      </div>
      <button type="submit">Confirm Payment</button>
    </form>
  </div>
</template>
<script>
/*
In this example, we created a form with input fields for the client name, invoice number, payment amount, and transaction link. We added  v-model  directives to bind the values of the form fields to our component's data properties. We also added a submit button to confirm the payment. 
 When the client submits the form, the  submitPayment  method is called. Here, you can add your logic to confirm the payment and update the invoice data accordingly. In this example, we simply log the payment confirmation object to the console. 
 After confirming the payment successfully, reset the form fields to their initial values so the client can confirm another payment.
*/
export default {
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
