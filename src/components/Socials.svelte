<script lang="ts">
  function copyToClipboard() {
    navigator.clipboard.writeText('miquel97bdn@gmail.com')
  }
</script>

<style lang="scss">
  .socials {
    display: flex;
    padding: 20px 0;
    gap: 20px;

    img {
      transition: 0.3s ease;
      filter: grayscale(1);
      opacity: 0.2;

      &:hover {
        transition: 0.3s ease;
        opacity: 1;
      }
    }
  }
</style>

<div class="socials">
  <a href="https://www.linkedin.com/in/miquel-toran-surina/" target="_blank" title="LinkedIn">
    <img src="/assets/linkedin.png" alt="Linkedin" height="50px" />
  </a>
  <a href="https://github.com/xScripted" target="_blank" title="Github">
    <img src="/assets/github.png" alt="Github" height="50px" />
  </a>
  <a href="mailto:miquel97bdn@gmail.com" target="_blank" title="miquel97bdn@gmail.com">
    <img src="/assets/email.png" alt="Email" height="50px" />
  </a>
</div>
