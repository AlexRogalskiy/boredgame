<script lang="ts">
  import { boredState } from '$lib/stores/boredState';

  let submitting = $boredState?.loading;
  let minAge = 1;
  let minPlayers = 1;
  let maxPlayers = 1;
  let exactMinPlayers = false;
  let exactMaxPlayers = false;
</script>

<!-- <form on:submit|preventDefault={handleSubmit} method="post"> -->
<fieldset class="advanced-search" aria-busy={submitting} disabled={submitting}>
  <div>
    <label for="minAge">
      Min Age
      <input id="minAge" name="minAge" bind:value={minAge} type="number" min={1} max={120} />
    </label>
  </div>
  <div>
    <label for="minPlayers">
      Min Players
      <input
        id="minPlayers"
        name="minPlayers"
        bind:value={minPlayers}
        type="number"
        min={0}
        max={50}
      />
    </label>
    <label for="exactMinPlayers" style="display: flex; gap: 1rem; place-items: center;">
      <span>Exact?</span>
      <input
        id="exactMinPlayers"
        type="checkbox"
        name="exactMinPlayers"
        bind:checked={exactMinPlayers}
      />
    </label>
  </div>
  <div>
    <label for="maxPlayers">
      Max Players
      <input
        id="maxPlayers"
        name="maxPlayers"
        bind:value={maxPlayers}
        type="number"
        min={0}
        max={50}
      />
    </label>
    <label for="exactMaxPlayers" style="display: flex; gap: 1rem; place-items: center;">
      <span>Exact?</span>
      <input
        id="exactMaxPlayers"
        type="checkbox"
        name="exactMaxPlayers"
        bind:checked={exactMaxPlayers}
      />
    </label>
  </div>
</fieldset>
<!-- <button type="submit" disabled={submitting}>Submit</button> -->

<!-- </form> -->
<style lang="scss">
  fieldset {
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    @media (max-width: 800px) {
      grid-template-columns: 1fr;
    }
  }

  label {
    display: grid;
    margin: 1rem;
  }
</style>
