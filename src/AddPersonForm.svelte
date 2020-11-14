<script>
  let name;
  let beltColour;
  let age;
  //   let reading = false;
  //   let listening = false;
  //   let running = false;
  let skills = [];

  const handleSubmit = () => {
    // console.log(name, beltColour, age, reading, listening, running);
    console.log(name, beltColour, age, skills);
  };
</script>

<style>
</style>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <!-- <input type="text" placeholder="belt colour" bind:value={beltColour} /> -->
  <input type="number" placeholder="age" bind:value={age} />

  <label>Skills:</label>
  <!-- <input type="checkbox" bind:checked={reading} />Reading<br />
  <input type="checkbox" bind:checked={listening} />Listenging<br />
  <input type="checkbox" bind:checked={running} />Running<br /> -->

  <input type="checkbox" bind:group={skills} value="reading" />Reading<br />
  <input type="checkbox" bind:group={skills} value="listening" />Listening<br />
  <input type="checkbox" bind:group={skills} value="running" />Running<br />

  <label>Belt Colour:</label>
  <select bind:value={beltColour}>
    <option value="black">Black</option>
    <option value="red">Red</option>
    <option value="orange">Orange</option>
    <option value="white">White</option>
  </select>
  <button>Add Person</button>
</form>
