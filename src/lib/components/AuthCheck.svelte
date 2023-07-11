<script lang="ts">
  import { user } from "$lib/firebase";
</script>

{#if $user}
  <slot />
{:else}
  <p class="text-lg text-red-300">your not login! please log in first</p>
  <br>
  <a href="/login" class="btn btn-warning">go to login</a>
{/if}
