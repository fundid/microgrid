<script>
    import {
    DataTable,
    Toolbar,
    ToolbarContent,
    ToolbarSearch,
    ToolbarMenu,
    ToolbarMenuItem,
    Button,
    Pagination,
  } from "carbon-components-svelte";

  // let rows = Array.from({ length: 10 }).map((_, i) => ({
  //   id: i,
  //   name: "Load Balancer " + (i + 1),
  //   protocol: "HTTP",
  //   port: 3000 + i * 10,
  //   rule: i % 2 ? "Active" : "Inactive",
  // }));
  let pageSize = 5;
  let page = 1;
  let filteredRowIds = [];

  $: console.log("filteredRowIds", filteredRowIds);

  </script>
  
  <!-- <h1>Users</h1> -->

  <DataTable
    title="Users"
    description="Your organization's registered users."
    expandable
    sortable
    stickyHeader
    shouldFilterRows
    zebra
    headers={[
      { key: "name", value: "Name" },
      { key: "protocol", value: "Gender" },
    { key: "type", value: "Membership Type",/* sort: false*/ },
      { key: "active", value: "Active" },
    ]}
    rows={[
      {
        id: "a",
        name: "Generic User 3",
        protocol: "M",
        type: "Member",
        active: "Active",
      },
      {
        id: "b",
        name: "Generic User 1",
        protocol: "M",
        type: "Staff",
        active: "Active",
      },
      {
        id: "c",
        name: "Generic User 2",
        protocol: "F",
        type: "Non-member Staff",
        active: "Inactive",
      },
      {
        id: "d",
        name: "Generic User 6",
        protocol: "F",
        type: "Member",
        active: "Active",
      },
      {
        id: "e",
        name: "Generic User 4",
        protocol: "M",
        type: "Member",
        active: "Active",
      },
      {
        id: "f",
        name: "Generic User 5",
        protocol: "F",
        type: "Staff",
        active: "Inactive",
      },
    ]}

  {pageSize}
  {page}
  >
  <svelte:fragment slot="expanded-row" let:row>
    <pre>{JSON.stringify(row, null, 2)}</pre>
  </svelte:fragment>
  <Toolbar>
    <ToolbarContent>
      <ToolbarSearch />
      <ToolbarMenu>
        <ToolbarMenuItem primaryFocus>Some option</ToolbarMenuItem>
        <ToolbarMenuItem href="https://somelink.com">
          Documentation
        </ToolbarMenuItem>
        <ToolbarMenuItem hasDivider danger>Delete all</ToolbarMenuItem>
      </ToolbarMenu>
      <Button>Create user</Button>
    </ToolbarContent>
  </Toolbar>
  </DataTable>
  
  <Pagination
  bind:pageSize
  bind:page
  totalItems={filteredRowIds.length}
/>