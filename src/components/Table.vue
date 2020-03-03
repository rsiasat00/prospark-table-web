<template>
  <div>
    <table id="dataTable" class="table">
      <thead>
        <tr>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Email</th>
        </tr>
      </thead>
    </table>
  </div>
</template>

<script>
import $ from "jquery";
import "datatables.net-bs4";
import "datatables.net-buttons-bs4";

export default {
  mounted() {
    $("#dataTable").DataTable({
      processing: true,
      serverSide: true,
      paging: true,
      ajax: (process.env.VUE_APP_API_URL ? process.env.VUE_APP_API_URL : "http://127.0.0.1:8000") + "/api/users"
    });
  }
};
</script>

<style>
#dataTable {
  text-align: left;
  margin: 1rem;
}
</style>