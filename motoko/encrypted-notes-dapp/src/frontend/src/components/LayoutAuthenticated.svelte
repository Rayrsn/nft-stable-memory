<script lang="ts">
  import { Router } from 'svelte-router-spa';
  import '../store/notes';
  import Devices from './Devices.svelte';
  import EditNote from './EditNote.svelte';
  import NewNote from './NewNote.svelte';
  import Notes from './Notes.svelte';
  import SidebarLayout from './SidebarLayout.svelte';

  const routes = [
    {
      name: '/',
      component: NewNote,
    },
    {
      name: '/notes',
      nestedRoutes: [
        { name: 'index', component: Notes },
        { name: 'edit/:id', component: EditNote },
      ],
    },
    {
      name: '/devices',
      component: Devices,
    },
  ];
</script>

<SidebarLayout>
  <Router {routes} />
</SidebarLayout>
