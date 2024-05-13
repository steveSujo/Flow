<script lang="ts">



export let options;
let selected = options[0];
$: focus = false;

// function selectele(e) {

// console.log(e);
// }

function select(ob){
focus =false;
return selected = ob;
}
</script>
<div class="w-1/4">
<div class="cus-select cursor-pointer" on:click={() =>focus = !focus}>
	<div>{selected.name}</div>
	<div class="font-semibold">${selected.balance}</div>
</div>

{#if focus}
	
<div class="bg-base-200 cursor-pointer cus-option">
	{#each options as item}
	<div on:click={select(item)} class="opt">
		<div>{item.name}</div>
		<div class="font-semibold">${item.balance}</div>
	</div>
	{/each}
</div>
{/if}
</div>

<style lang="postcss">
.cus-select {
  @apply bg-base-100 rounded border pr-10 border-base-content/20 flex justify-between p-2 ;
  background-image: linear-gradient(45deg, transparent 50%, currentcolor 50%),
    linear-gradient(135deg, currentcolor 50%, transparent 50%);
  background-position:
    calc(100% - 20px) calc(1px + 50%),
    calc(100% - 16.1px) calc(1px + 50%);
  background-size:
    4px 4px,
    4px 4px;
  background-repeat: no-repeat;
  &:focus {
    box-shadow: none;
    @apply border-base-content/20 outline-base-content/20 outline outline-2 outline-offset-2;
  }
  & select {
	display: none;
  }
  & > option{
@apply flex justify-between;
  }

}

.cus-option {
  @apply bg-base-100 rounded border border-base-content/20 flex flex-col p-1 absolute w-1/5 z-10;

  & .opt {
@apply flex justify-between  hover:bg-base-300 w-full my-1 p-1 rounded-sm ;
  }
}

[dir="rtl"] .cus-select {
  background-position:
    calc(0% + 12px) calc(1px + 50%),
    calc(0% + 16px) calc(1px + 50%);
}
</style>