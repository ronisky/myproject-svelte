<script>
  import Modal from "./Modal.svelte";
  import AddPersonForm from "./AddPersonForm.svelte";

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

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

  // let num = 6;

  const addPerson = (e) => {
    // console.log(e.detail);
    const person = e.detail;
    people = [person, ...people];
    showModal = false;
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

<!-- {#if num > 20}
  <p>Greater than 20</p>
{:else if num > 5}
  <p>Greater than 5</p>
{:else}
  <p>Not greater than 5</p>
{/if} -->

<!-- <Modal message="Hey, I am PesantechID a prop value " isPromo={true} /> -->
<!-- <Modal
  message="Hey, I am PesantechID a prop value again"
  {showModal}
  on:click={toggleModal} /> -->
<Modal {showModal} on:click={toggleModal}>
  <!-- <h3>Add a new person</h3>
  <form action="">
    <input type="text" placeholder="name" />
    <input type="text" placeholder="belt colour" />
    <button>Add Person</button>
  </form> -->
  <!-- <div slot="title">
    <h3>Add a new person</h3>
  </div> -->
  <AddPersonForm on:addPerson={addPerson} />
</Modal>

<main>
  <button on:click={toggleModal}>Open Modal</button>
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
      {#if person.beltColour === 'black'}
        <p><strong>Pesantech ID</strong></p>
      {/if}
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
