<script>
  let firstName = "Roni";
  let lastName = "Setiawan";
  let beltColour = "black";

  $: fullName = `${firstName} ${lastName}`;
  $: {
    console.log(beltColour);
    console.log(fullName);
  }

  const handleClick = () => {
    beltColour = "orange";
  };

  const handleInput = (e) => {
    beltColour = e.target.value;
  };
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <!-- <h1>Hello {name}!</h1> -->
  <!-- <p>{firstName}{lastName}-{beltColour} blet</p> -->
  <p>{fullName}-{beltColour} blet</p>
  <!-- <button on:click={handleClick}>update belt colour</button> -->
  <!-- <input type="text" on:input={handleInput} value={beltColour} /> -->
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" bind:value={beltColour} />
</main>
