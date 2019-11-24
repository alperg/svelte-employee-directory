<script>
  import { Table } from 'sveltestrap';

  export let employees;
  console.log(employees);
</script>

<Table>
  <thead>
  <tr>
    <th>#</th>
    <th></th>
    <th>First Name</th>
    <th>Last Name</th>
    <th>Email</th>
    <th>Gender</th>
    <th>Department</th>
    <th>Start Date</th>
    <th>Days Worked</th>
  </tr>
  </thead>
  <tbody>
    {#each employees as emp}
      <tr>
        <td>{emp.id}</td>
        <td><img src={emp.avatar} alt="employee"></td>
        <td>{emp.firstName}</td>
        <td>{emp.lastName}</td>
        <td>{emp.email}</td>
        <td>{emp.gender}</td>
        <td>{emp.department}</td>
        <td>{emp.date}</td>
        <td>{emp.daysPassed}</td>
      </tr>
    {/each}
  </tbody>
</Table>
