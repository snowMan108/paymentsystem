<template>
  <!--  5. Payment Status Checker: The payment status checker will allow clients to check the status of their payments. It should include a field for the transaction link and display the payment status (paid or unpaid).  -->
  <div>
    <h1>Payment Status Checker</h1>
    <form @submit.prevent="checkPayment">
      <div class="form-group">
        <label for="txLink">Transaction Link:</label>
        <input type="text" id="txLink" v-model="txLink" required />
      </div>
      <button type="submit">Check Payment Status</button>
    </form>
    <div v-if="paymentStatus !== null">
      <h2 v-if="paymentStatus">Payment Status: Paid</h2>
      <h2 v-else>Payment Status: Unpaid</h2>
    </div>
  </div>
</template>
<script>
/*
In this example, we created a form with an input field for the transaction link. We added a  v-model  directive to bind the value of the input field to our component's  txLink  data property. We also added a submit button to check the payment status. 
 When the client submits the form, the  checkPayment  method is called. Here, you can add your logic to check the payment status based on the provided transaction link. In this example, we randomly generated the payment status using  Math.random() >= 0.5 . 
 After checking the payment status, we update the  paymentStatus  data property with either  true  (paid) or  false  (unpaid). We also conditionally render a  <h2>  element to display the payment status to the client. If  paymentStatus  is  null , the payment status is not displayed. Once the client submits the form again, the payment status will be updated based on the new transaction link.
*/
export default {
  data() {
    return {
      txLink: "",
      paymentStatus: null,
    };
  },
  methods: {
    checkPayment() {
      // Here you can add your logic to check the payment status based on the provided transaction link
      // For the sake of this example, we're going to randomly generate the payment status
      this.paymentStatus = Math.random() >= 0.5;
    },
  },
};
</script>
