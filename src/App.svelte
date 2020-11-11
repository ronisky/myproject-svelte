<script>
  let people = [
    { name: "roni", beltColour: "black", age: 20, id: 1 },
    { name: "rona", beltColour: "orange", age: 21, id: 2 },
    { name: "kaka", beltColour: "blue", age: 22, id: 3 },
  ];

  const handleClick = (id) => {
    // delete the persn from people
    // console.log(id);
    people = people.filter((person) => person.id != id);
  };
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  /* h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  } */

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <!-- <div>
    <h4>{people[0].name}</h4>
    <p>{people[0].beltColour}</p>
  </div>
  <div>
    <h4>{people[1].name}</h4>
    <p>{people[1].beltColour}</p>
  </div>
  <div>
    <h4>{people[2].name}</h4>
    <p>{people[2].beltColour}</p>
  </div> -->
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} years old, {person.beltColour} belt.</p>
      <button
        on:click={() => {
          handleClick(person.id);
        }}>delete</button>
    </div>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>
