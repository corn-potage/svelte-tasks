<script>
  let isLoggedIn = false;
  let user = null;

  function login() {
    // Implement login logic
    isLoggedIn = true;
    user = { name: 'John Doe' };
  }

  function logout() {
    isLoggedIn = false;
    user = null;
  }
</script>

<header class="flex justify-between items-center p-4 bg-white shadow-md">
  <div class="flex items-center">
    <img src="/logo.svg" alt="Bounty" class="h-8 mr-4" />
    <nav>
      <a href="/" class="mr-4">Bounties</a>
      <a href="/how-it-works" class="mr-4">How It Works</a>
      <a href="/sponsors">Sponsors</a>
    </nav>
  </div>
  <div>
    {#if isLoggedIn}
      <div class="flex items-center">
        <span class="mr-4">{user.name}</span>
        <button on:click={logout}>Logout</button>
      </div>
    {:else}
      <button on:click={login}>Login</button>
    {/if}
  </div>
</header>