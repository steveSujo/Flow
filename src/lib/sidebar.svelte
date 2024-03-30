<script lang="ts">
	import Sidebaritem from './sidebaritem.svelte';
</script>

<div class="drawer bg-base-100 drawer-open">
    <input id="sidebar" type="checkbox" class="drawer-toggle"/>
    <div class="drawer-content bg-base-200">
    <!-- <label for="sidebar" class="btn btn-primary drawer-button lg:hidden">open sidebar</label> -->
<div class="max-w-[100vw] px-10 pb-16 xl:pr-10"> <slot/>
</div>
    </div>
	<div class="drawer-side">
        <label for="sidebar" aria-label="close sidebar" class="drawer-overlay"></label>
<aside class="bg-base-100 min-h-screen w-80">
<div>

</div>
<ul class="menu px-4 py-0 ">
        <li>
		<Sidebaritem name="Dashboard" route="/" />
        </li> <li>
		<Sidebaritem name="Inventory" route="/inventory/" />
        </li>
        <li>
		<Sidebaritem name="Invoices" route="/invoices/" />
        </li>
        <li>
		<Sidebaritem name="Transactions" route="/transactions" />
        </li>
        <li>
		<Sidebaritem name="Account" route="/accounts/" />
        </li>
        <li>
		<Sidebaritem name="Reports" route="/reports/" />
        </li>
        <li>
    	<Sidebaritem name="Settings" route="/settings/" />
        </li>
</ul>
</aside>
</div>
</div>

