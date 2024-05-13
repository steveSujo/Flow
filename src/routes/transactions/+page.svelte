
<script lang="ts">
	import TransactionItem from "$lib/TransactionItem.svelte";
	import SelectInput from "$lib/SelectInput.svelte";
type trans = {
select:Boolean,
date:Date,
des:String,
account:String,
cate:String,
income:Boolean,
amount:float,
}
    let translist: trans[] = [];
    // list of accounts to show their balances
    // TODO accounts with cash
    let accounts = [{name:"All accounts",balance:23},{name:"Cash in hand",balance:12},{name:"Bank",balance:43}]
let date = new Date();

function addIncome() {
let trans:trans =  {select:false,date,des:"",account:"",cate:"",amount:0.00,income:true};
    translist.unshift(trans);
    translist = translist;
    // editTrans = true;
}
function addExpense() {
let trans:trans =  {select:false,date,des:"",account:"",cate:"",amount:0.00,income:false};
    translist.unshift(trans);
    translist = translist;
    // editTrans = true;
}

$: translist;
let editTrans = false;
let amount = 10;
</script>
<div class="py-2">
<div class="flex justify-between my-4">
<span class="text-3xl font-semibold">Transactions</span>

<div class="join">
<div class="btn join-item  btn-primary btn-outline" on:click={addIncome}>Add Income</div>
<div class="btn join-item btn-outline" on:click={addExpense}>Add Expenses</div>
</div>

</div>

<!-- account balances -->
<!-- <div class="dropdown dropdown-end w-1/5">

    <div tabindex="0" role="button" class="bg-base-300 m-1 px-2 py-2 justify-between flex rounded-md">
        <div> All accounts </div>
<div class="font-bold">$ 00</div>
    </div>
    <ul tabindex="0" class="dropdown-content z-[1] menu p-2 shadow bg-base-200 rounded-box w-52">
    <li><a>item 1</a></li>
    <li><a>item 2</a></li>
    </ul>
</div> -->

<!-- <select class="select select-bordered w-full max-w-xs">
  <option selected value="all ac" class="flex justify-between">
    <div>All account</div>
    <div class="font-bold">$0</div>
</option>
  <option>Homer</option>
  <option>Marge</option>
  <option>Bart</option>
  <option>Lisa</option>
  <option>Maggie</option>
</select> -->

<SelectInput  options={accounts}/>

<!-- table -->


<div class="table-container  my-2 border rounded">
<div class="form-control table-controls bg-base-200 text-base-content w-full">
<div class="px-4 h-12 py-2">
<label class="label cursor-pointer max-w-24">
<input type="checkbox" class="checkbox checkbox-primary checkbox-sm">
    <span class="label-text">Select all</span>
</label>
</div>
<div class="bg-base-100">
    <table class="table">
        <thead>
            <tr>
                <th></th>
                <th>Date</th>
                <th>Discription</th>
                <th>Account</th>
                <th>Category</th>
                <th>Amount</th>
                <th>Actions</th>
            </tr>
        </thead>
        <tbody>
            {#each translist as trans}
               <TransactionItem infoObject={trans} /> 
            {/each}
        </tbody>
    </table>
</div>
</div>
{#if editTrans}
<div class="border-l-2 w-full">
<div class="flex items-center justify-between border-b-base-300 border-b-2 px-4">
    <div class="text-lg  text-base-content h-max">
Edit transaction details
    </div>
<div class="btn btn-square" on:click={()=>editTrans= !editTrans}>
<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
</svg>
</div>

   </div> 

<div class="px-4">
    <label for="form-control w-full max-w-xs">
        <div class="label-text label" >
        Description
        </div>
    <input type="text" class=" mb-2 input-lg font-semibold input input-bordered w-full">

    <div class="join w-full">
    <div class="w-full">
        Account
    <div>
    <input type="text" class="w-full input join-item input-bordered ">
    </div>
    </div>
    <div class="w-full">

        Date
    <div>
    <input type="date" class="w-full input join-item input-bordered ">
    </div>
    </div>
    </div>


    <div class="join w-full">
    <div class="w-full">
        Deposit or Withdrawal
    <div>
    <!-- <input type="text" class="w-full input join-item input-bordered "> -->
    <select name="type" id="" class="select w-full select-bordered join-item">
        <option value="deposit">Deposit</option>
        <option value="withdraw">Withdrawal</option>
    </select>
    </div>
    </div>
    <div class="w-full tex">
        Total amount
    <div>
    <input type="input" class="text-right w-full input join-item input-bordered ">
    </div>
    </div>
    </div>


    </label>

</div>
   <!-- <div class="divider"></div> -->
</div>
{/if}
</div>

</div>

<style lang="postcss">
.table-container {
    @apply bg-base-200 flex; 

}

input[type="date"] {
@apply cursor-pointer;
}

</style>