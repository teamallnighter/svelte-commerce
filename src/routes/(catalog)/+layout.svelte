<script lang="ts">
import { Footer, Nav } from '$lib/theme-config'
import { PageTransitions } from '$lib/components'

export let data

let showCartSidebar = false
let openSidebar = false
</script>

<div class="{showCartSidebar || openSidebar ? 'h-screen overflow-hidden' : 'h-full'}">
	<Nav
		me="{data.me}"
		cart="{data.cart}"
		store="{data.store}"
		q="{data.q}"
		class="hidden lg:block"
		bind:showCartSidebar
		bind:openSidebar />

	<PageTransitions url="{data.url}">
		<slot />
	</PageTransitions>

	<div class="hidden lg:block">
		<Footer />
	</div>
</div>
