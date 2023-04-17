<template>
  <div>
    <!--- 2. Invoice Generator: The invoice generator will allow users to create new invoices. It should include fields for the client name, invoice amount, due date, and other necessary details. --->

    <h1>Invoice Generator</h1>
    <form @submit.prevent="submitInvoice">
      <div class="form-group">
        <label for="clientName">Client Name:</label>
        <input type="text" id="clientName" v-model="clientName" required />
      </div>
      <div class="form-group">
        <label for="invoiceAmount">Invoice Amount:</label>
        <input
          type="number"
          id="invoiceAmount"
          v-model="invoiceAmount"
          required
        />
      </div>
      <div class="form-group">
        <label for="dueDate">Due Date:</label>
        <input type="date" id="dueDate" v-model="dueDate" required />
      </div>
      <div class="form-group">
        <label for="otherDetails">Other Details:</label>
        <textarea id="otherDetails" v-model="otherDetails"></textarea>
      </div>
      <button type="submit">Generate Invoice</button>
    </form>
  </div>
</template>

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
