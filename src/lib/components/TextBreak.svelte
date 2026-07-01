<script>
  let { heading, children } = $props();
</script>

<div class="h-[160vh]">
  <div
    class="sticky top-0 mx-auto flex h-screen w-[88vw] flex-col justify-center font-sans text-base-content lg:ml-[calc(43%-400px)] lg:w-200"
  >
    <h2 class="text-2xl font-semibold sm:text-3xl">{heading}</h2>
    <div class="mt-6 space-y-4 text-lg leading-relaxed text-base-content/80">
      {@render children()}
    </div>
    <div class="divider mt-10"></div>
  </div>
</div>
