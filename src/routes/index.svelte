<script>
    let Name = ""
    let Age = ""

    async function getAge() {
  fetch('https://api.agify.io/?name=' + Name)
	.then((response) => response.json())
	.then((data) => { // Path for temperature
  	Age = data.age; // Path for description
	});
}
</script>

<h1>Guess my Age App</h1>
<p>Age:{Age}</p>

<form on:submit|preventDefault={getAge}>
    <label for="name">Name : </label>
    <input id="name" bind:value={Name} type="text" />
    <button type="name">Check</button>
</form>