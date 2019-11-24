<script>
  import {
    Collapse,
    Navbar,
    NavbarBrand,
    Form,
    Input
  } from 'sveltestrap';

  let isOpen = false;

  function handleUpdate(event) {
    isOpen = event.detail.isOpen;
  }
</script>

<Navbar color="primary" dark>
  <NavbarBrand href="/" class="mr-auto">Svelte Employee Directory</NavbarBrand>
  
  <Form class="form-inline">
    <Input
      class="form-control mr-sm-2"
      type="text"
      name="searchTerm"
      value=""
      placeholder="search..."
      onChange=""
      readonly="false"
    />
  </Form>
  
</Navbar>
