<script setup>
import JSConfetti from 'js-confetti'

const confetti = new JSConfetti()

function showConfetti() {
  confetti.addConfetti()
}

showConfetti()
</script>