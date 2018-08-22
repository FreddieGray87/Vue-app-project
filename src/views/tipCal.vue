<template>
<div class="container mt-3 mt-sm-5" id="app">
  <div class="row justify-content-center mb-4">
    <div class="col-md-4">
      <div class="input-group">
        <div class="input-group-addon">$</div>
        <input class="form-control" type="number" v-model="input"/>
      </div>
    </div>
  </div>
  <div class="row justify-content-center" v-if="input">
    <div class="col-md-6">
      <table class="table">
        <thead>
          <tr>
            <th></th>
            <th>15%</th>
            <th>18%</th>
            <th>20%</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th>Tip</th>
            <td>${{ fifteen }}</td>
            <td>${{ eighteen }}</td>
            <td>${{ twenty }}</td>
          </tr>
          <tr>
            <th>Total</th>
            <td>${{ tFifteen }}</td>
            <td>${{ tEighteen }}</td>
            <td>${{ tTwenty }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

</template>

<script>
export default {
  name: "Cal",
    data: { input: null },
      computed: {
        fifteen: function() {
          return (this.input * 0.15).toFixed(2);
        },
        eighteen: function() {
          return (this.input * 0.18).toFixed(2);
        },
        twenty: function() {
          return (this.input * 0.2).toFixed(2);
        },

        tFifteen: function() {
          return (this.input + +this.fifteen).toFixed(2);
        },
        tEighteen: function() {
          return (this.input + +this.eighteen).toFixed(2);
        },
        tTwenty: function() {
          return (this.input + +this.twenty).toFixed(2);
        }
      }
    };
  </script>
<style>
.input-group-addon,
.form-control {
  font-size: 30px;
}
</style>
