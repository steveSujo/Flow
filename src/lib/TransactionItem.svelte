
<script lang="ts">
export let infoObject: Object;

// orginal = infoObject

// function keydown(event) {
// if (event.key == "Escape" ) {
//    event.preventDefault();
// infoObject = orginal;
// }
// }

</script>

<tr class:bg-base-200={infoObject.select} class="hover:bg-neutral-200/25">
            <th>
<input type="checkbox" class="checkbox checkbox-primary checkbox-sm p-0" bind:checked={infoObject.select}>
            </th>
            <th>{infoObject.date}</th>
            <th>{infoObject.des}</th>
            <th>{infoObject.account}</th>
            <th>{infoObject.cate}</th>
					 {#if infoObject.income}
            <th class="text-success">{infoObject.amount}</th>
			{:else}
            <th class="">{infoObject.amount}</th>
			
					 {/if}
            <th>
                <button class="btn btn-circle btn-outline btn-sm">#tick#</button>
<div class="dropdown dropdown-end w-1/5">
    <div tabindex="0" role="button" class="btn btn-circle btn-outline btn-sm">
        <div>v</div>
    </div>
    <ul tabindex="0" class="dropdown-content z-[1] menu p-2 shadow bg-base-200 rounded-box w-52">
    <li><a>item 1</a></li>
    <li><a>item 2</a></li>
    </ul>
</div>
            </th>
        </tr>

