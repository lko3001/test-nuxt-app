<template>
  <h1 class="font-medium mb-4 text-3xl">Global Thoughts</h1>
  <button v-if="!user" @click="handleSignIn">SignIn</button>
  <button v-else @click="handleSignOut">SignOut</button>

  <pre>{{ user }}</pre>
  <section class="flex flex-col gap-4">
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
    <Card />
  </section>
</template>

<script setup lang="ts">
const { status, data, signIn, signOut } = useAuth();

async function handleSignIn() {
  await signIn(undefined);
}

async function handleSignOut() {
  await signOut();
}

const user = computed(() => (data.value ? data.value.user : data.value));
</script>
