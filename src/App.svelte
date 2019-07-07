<script>
	import { Router, Link, Route } from "svelte-routing";
	import * as routes from './constants/routes'

	import Login from './pages/Login.svelte'
	import Landing from './pages/Landing.svelte'
</script>

<Router url="">
	<Route path={routes.LANDING}><Landing /></Route>
	<Route path={routes.LOGIN}><Login /></Route>
</Router>

