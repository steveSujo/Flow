<script lang="ts">
	import Table from '$lib/table.svelte';

    const invoke = window.__TAURI__.invoke

    let res = invoke('get_accounts').then((string)=>{return JSON.parse(string)});

console.log(res);

	let columns = ['account_id', 'account_name', 'account_type', 'time_stamp'];
</script>

<div>
	<p>Accounts: page data :test</p>

    {#await res}
    <div class="skeleton w-32 h-32"></div>
    {:then rows}
	<Table {rows} {columns}></Table>
    {/await}

</div>

