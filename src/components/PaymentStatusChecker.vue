<template>
  <div class="max-w-md mx-auto">
    <h1 class="text-3xl font-bold text-center mb-6 mt-10">
      Payment Status Checker
    </h1>
    <form
      class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4"
      @submit.prevent="checkPayment"
    >
      <div class="mb-4">
        <label class="block text-gray-700 font-bold mb-2" for="txLink"
          >Transaction Link</label
        >
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
          id="txLink"
          type="text"
          v-model="txLink"
          required
        />
      </div>
      <div class="flex items-center justify-between">
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="submit"
        >
          Check Payment Status
        </button>
      </div>
    </form>
    <div class="text-center" v-if="paymentStatus !== null">
      <h2 class="text-2xl font-bold" v-if="paymentStatus">
        Payment Status: <span class="text-green-500">Paid</span>
      </h2>
      <h2 class="text-2xl font-bold" v-else>
        Payment Status: <span class="text-red-500">Unpaid</span>
      </h2>
    </div>
  </div>
</template>
<!--
  In this code, we've added several Tailwind CSS classes to style the form and make it more visually appealing. We've added a max width to center the form, a shadow and rounded corners to give it some depth, and a blue background color for the button. 
 
We've also customized the text and input fields with different shades of gray, and added some spacing between the elements in the form. 
 
Lastly, we've added a conditional statement to display the payment status once the user submits the form. The text is styled with an appropriate font size and font weight, and the payment status is displayed in green or red, depending on whether it's paid or unpaid.
  --->
<script>
/*
In this example, we created a form with an input field for the transaction link. We added a  v-model  directive to bind the value of the input field to our component's  txLink  data property. We also added a submit button to check the payment status. 
 When the client submits the form, the  checkPayment  method is called. Here, you can add your logic to check the payment status based on the provided transaction link. In this example, we randomly generated the payment status using  Math.random() >= 0.5 . 
 After checking the payment status, we update the  paymentStatus  data property with either  true  (paid) or  false  (unpaid). We also conditionally render a  <h2>  element to display the payment status to the client. If  paymentStatus  is  null , the payment status is not displayed. Once the client submits the form again, the payment status will be updated based on the new transaction link.
*/
export default {
  name: "PaymentStatusChecker",
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
