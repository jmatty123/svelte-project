<script lang="ts">
    import type { PageData } from './$types';
    import { superForm } from 'sveltekit-superforms/client';
  
    export let data: PageData;
  
    // Client API:
    const { form } = superForm((data as any).form);
  </script>
  
  <form method="POST">
    <label for="name">Name</label>
    <input type="text" name="name" bind:value={$form.name} />
  
    <label for="email">E-mail</label>
    <input type="email" name="email" bind:value={$form.email} />
  
    <div><button>Submit</button></div>
  </form>