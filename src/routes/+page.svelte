<script lang="ts">
import BarGraph from "$lib/BarGraph.svelte";
import * as d3 from "d3";

let data = d3.ticks(2,-10,30).map(Math.tan);

</script>

<div class="flex justify-between my-4">
<span class="text-2xl">Dashboard</span>
<input type="text" placeholder="search" class="input w-full max-w-xs">
</div>

<div class="stats shadow mb-4">
<div class="stat w-96 bg-base-100 shadow-sm mx-1">
<h1 class="stat-title">Income</h1>
<div class="stat-value text-success">$20</div>
<div class="stat-desc">placeholder info</div>
</div>

<div class="stat join-item w-96 bg-base-100 shadow-sm mx-1">
<div class="stat-title">Expenses</div>
<div class="stat-value text-error">$20</div>
<div class="stat-desc">placeholder info</div>
</div>
</div>

<div class="flex justify-between ">
<div class="card mr-10 w-1/2 max-w-2xl bg-base-100 shadow">

<div class="p-0 card-body">
<div class="card-title-padding card-title text-base-content">

Recent Transactions </div>

<table class="table table-zebra">

<thead>
<tr>
<th>
</th>
<th>
Description
</th>
<th>
Date
</th>
<th>
Amount
</th>
</tr>
</thead>


<tbody>
<tr>
<td>
1
</td>
<td>
paid for something
</td>
<td>
9th of Feb
</td>
<td>
-$20
</td>
</tr>


<tr>
<td>
2
</td>
<td>
paid for something
</td>
<td>
9th of Feb
</td>
<td>
-$40
</td>
</tr>

<tr>
<td>
3
</td>
<td>
paid for something
</td>
<td>
9th of Feb
</td>
<td>
-$30
</td>
</tr>

<tr>
<td>
4
</td>

<td>
paid for something
</td>

<td>
9th of Feb
</td>

<td>
-$30
</td>
</tr>

</tbody>
</table>

</div>
</div>

<div class="card bg-base-100  min-w-fit w-1/2 text-base-content">
<div class="card-title card-title-padding">Place Holder for cashflow Chart</div>
<div class="card-body">
<BarGraph data={data}/>
</div>
</div>
</div>

<div class="card bg-base-100 shadow"> 
<div class="card-body"> 
<p>
sierra
</p>
</div> 
</div> 

<style lang="postcss">

.card-title-padding {

margin-left: var(--padding-card,2rem);
margin-top: var(--padding-card,2rem);

    }

</style>
