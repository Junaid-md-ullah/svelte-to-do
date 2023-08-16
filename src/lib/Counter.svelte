<script>
  let count = 0;
  let color = 'blue';
  let showText = false;
  let users = [
    {
      id: '1',
      name: 'John'
    },
    {
      id: '2',
      name: 'Sarah'
    },
    {
      id: '3',
      name: 'Bob'
    }
  ];
  const increment = () => {
    count += 1
  }
  
  const toggle = () =>{
    color = color === 'blue' ? 'red' : 'blue';
    showText = !showText;
    users = [...users, {id: '4', name: 'Jen'}];
  }
</script>

<button on:click={increment} style="color: {color}">
  count is {count}
</button>

<button on:click={toggle}>
  click
</button>

{#if showText}
  <p>Hello svelte the bitch</p>
  {:else}
  <p>No Text</p>
{/if}

{#each users as user(user.id)}
  <h3>{user.id}: {user.name}</h3>
{/each}
