<script>
	import { Router, Link, Route } from "svelte-routing";
	import * as routes from './constants/routes'

	import Landing from './pages/Landing.svelte'
</script>

<Router url="">
	<Route path={routes.LANDING}><Landing /></Route>
</Router>

