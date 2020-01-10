<script>
	let user = { loggedIn: false };

	function toggle() {
		user.loggedIn = !user.loggedIn;
	}
</script>

<h1>if文を書いてログインとログアウトが交互に押せるようにしよう!</h1>
	<button on:click={toggle}>
		Log out
	</button>

	<button on:click={toggle}>
		Log in
	</button>