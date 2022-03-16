<script>
	import { mdiMenu, mdiAccount, mdiBook, mdiHome, mdiWidgets } from '@mdi/js';
	import { base } from '$app/paths';

	let active = false;
	function toggleNavigation() {
		active = !active;
	}
	import {
		MaterialApp,
		Button,
		AppBar,
		CardText,
		Icon,
		List,
		ListItem,
		NavigationDrawer,
		Overlay
	} from 'svelte-materialify';

	let theme = 'light';

	function toggleTheme() {
		if (theme === 'light') theme = 'dark';
		else theme = 'light';
	}
</script>

<MaterialApp {theme}>
	<div style="position:relative;height:250px; color:grey;">
		<AppBar>
			<div slot="icon">
				<Button fab depressed on:click={toggleNavigation}>
					<Icon path={mdiMenu} />
				</Button>
			</div>
			<CardText>Svelte App</CardText>

			<button on:click={toggleTheme}>Toggle Theme</button>
			<img
				class="profile-kitten-img"
				style="float: right;"
				src="http://placekitten.com/100/100"
				alt="kitten"
			/>
		</AppBar>

		<NavigationDrawer absolute style="padding-top:50px;height:100vh;" {active}>
			<List>
				<ListItem>
					<span slot="prepend">
						<Icon path={mdiHome} />
					</span>
					<a href="{base}/">Home</a>
				</ListItem>
				<ListItem>
					<span slot="prepend">
						<Icon path={mdiAccount} />
					</span>
					<a href="{base}/customers">Customers</a>
				</ListItem>
				<ListItem>
					<span slot="prepend">
						<Icon path={mdiBook} />
					</span>
					Orders
				</ListItem>
				<ListItem>
					<span slot="prepend">
						<Icon path={mdiWidgets} />
					</span>
					Products
				</ListItem>
			</List>
		</NavigationDrawer>
		<Overlay {active} relative on:click={toggleNavigation} index={1} />
		<slot />
	</div>
</MaterialApp>

<style>
	.profile-kitten-img {
		display: inline-block;
		border-radius: 50%;
		height: 100%;
		background-repeat: no-repeat;
		background-position: center center;
		background-size: cover;
	}

	a {
		text-decoration: none;
		cursor: auto;
	}
</style>
