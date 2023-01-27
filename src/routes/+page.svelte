<script lang="ts">
  const showDot = [false, false, false];
  let intervalId;

    const animateDots = () => {
      intervalId = setInterval(() => {
        if (!showDot[0]) showDot[0] = true;
        else if (!showDot[1]) showDot[1] = true;
        else if (!showDot[2]) showDot[2] = true;
        else {
          resetAnimation();
        }
      }, 200);
    }

    const resetAnimation = () => {
      clearInterval(intervalId);
      setTimeout(() => {
        showDot[0] = false;
        showDot[1] = false;
        showDot[2] = false;
        animateDots();
      }, 500);
    }

    animateDots();
</script>

<main class="bg-gray-900 max-w-7xl mx-auto flex-1 flex items-center">
    <header class="w-full flex justify-center">
        <h1 class="text-3xl text-gray-400">The site is under construction
            <span class="dot {showDot[0] && 'visible'}">.</span >
            <span class="dot {showDot[1] && 'visible'}">.</span>
            <span class="dot {showDot[2] && 'visible'}">.</span>
        </h1>
    </header>
</main>
<footer class="max-w-7xl mx-auto py-2">
    <p class="text-gray-600">Tech TPD. Copyrights {new Date().getFullYear()}</p>
</footer>

<style>
    .dot {
        @apply opacity-0 transition-opacity duration-300;
    }
    .visible {
        @apply opacity-100;
    }
</style>
