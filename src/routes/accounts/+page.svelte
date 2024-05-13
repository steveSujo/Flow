<script lang="ts">
	import Table from '$lib/table.svelte';

    let columns = ["Si","Name","Description"]
    let rows = [["1","someting","sometime"],["2","sometingMore","TT"],["3","someThingElse","Sometime"]]

</script>

<div>
	<p>Accounts: page data :test</p>

    <!-- {#await res}
    <div class="skeleton w-32 h-32"></div>
    {:then rows}
	<Table {rows} {columns}></Table>
    {/await} -->


<Table {rows} {columns}></Table>
</div>

