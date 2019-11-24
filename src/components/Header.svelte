<script>
  import { Navbar, NavbarBrand, Form, Input } from 'sveltestrap';
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function onChange(event) {
    dispatch('change', event.target.value);
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
      on:keyup={onChange}
      readonly={false}
    />
  </Form>
  
</Navbar>
