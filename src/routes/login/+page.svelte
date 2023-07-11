<script lang="ts">
  import { auth } from "$lib/firebase";
  import { user } from "$lib/firebase";

  import { GoogleAuthProvider, signInWithPopup, signOut } from "firebase/auth";

  async function signInWithGoogle() {
    const provider = new GoogleAuthProvider();
    const user = await signInWithPopup(auth, provider);
    console.log(user);
  }
</script>

{#if $user}
  <h1 class="text-teal-300">welcome {$user.displayName}</h1>
  <br>
  <button class="btn btn-warning" on:click={() => signOut(auth)}>log out</button
  >
{:else}
  <p class="text-lg text-cyan-500">Login</p>
  <br>
  <button class="btn btn-primary" on:click={signInWithGoogle}
    >sign in with google</button
  >
{/if}
