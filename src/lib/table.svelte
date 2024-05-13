<script lang="ts">
	export let rows: string[][];
	export let columns: string[];
	let length = [...Array(columns.length).keys()];
</script>

<table class="table table-md">
    <thead>
	<tr>
		{#each columns as column}
			<th>{column}</th>
		{/each}
	</tr>
    </thead>
    <tbody>
	{#each rows as row}
		<tr class="tablerow">
	{#each length as column}
<td>{row[column]}</td>
	{/each}
		</tr>
	{/each}

	<!-- <tr class=""> -->
	<!-- 	<td>1</td> -->
	<!-- 	<td>someting</td> -->
	<!-- 	<td>something more</td> -->
	<!-- 	<td> #somethign</td> -->
	<!-- 	<td> /</td> -->
	<!-- </tr> -->
	<!---->
	<!-- <tr class=""> -->
	<!-- 	<td>2</td> -->
	<!-- 	<td>someting</td> -->
	<!-- 	<td>something more</td> -->
	<!-- 	<td> #somethign</td> -->
	<!-- 	<td> /</td> -->
	<!-- </tr> -->

    </tbody>
</table>

<style>
</style>
