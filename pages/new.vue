<template>
  <h1 class="font-medium mb-4 text-3xl">What are you thinking about?</h1>
  <textarea
    class="w-full min-h-[7rem] resize-none outline outline-neutral-300 rounded outline-1 p-4"
    placeholder="I was thinking about..."
    ref="ta"
    v-model="taContent"
  />
  <div class="text-right">
    <button class="bg-accent text-white rounded px-2 py-1">Post</button>
  </div>
</template>

<script setup>
const ta = ref(null);
const taContent = ref(null);

onMounted(() => {
  const textareaVar = ta._rawValue;

  if (textareaVar !== null) {
    textareaVar.setAttribute(
      "style",
      "height:" + textareaVar.scrollHeight + "px;overflow-y:hidden;"
    );
    textareaVar.addEventListener("input", OnInput, false);

    function OnInput() {
      this.style.height = 0;
      this.style.height = this.scrollHeight + "px";
    }
  }
});
</script>
