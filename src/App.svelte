<script>
  import Header from './components/Header.svelte';
  import EmployeeList from './components/EmployeeList.svelte';
  import API from './services/API';
  import moment from 'moment';
  
  export let employees = [];
  export let allEmployees = [];

  function fetchEmployees() {
    API.getEmployees().then(data => {
      const newData = data.map(emp => {
        const empStartDate = moment(emp.date, 'M/D/YYYY');
        emp.daysPassed = `${moment().diff(empStartDate, 'days')} days`;
        return emp;
      });
      employees = data;
      allEmployees = data;
    });
  }

  function onSearchChanged(searchTerm) {
    if (searchTerm === "") {
      this.fetchEmployees();
    } else {
      const filteredData = allEmployees.filter(emp =>
        emp.firstName.toLowerCase().indexOf(searchTerm.toLowerCase()) > -1);
      employees = filteredData;
    }
  }

  fetchEmployees();

</script>

<main>
	<Header></Header>
	<EmployeeList employees={employees}></EmployeeList>
</main>

<style>

</style>