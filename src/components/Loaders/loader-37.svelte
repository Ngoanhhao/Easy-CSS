<script>
  export let mainColor;
</script>

<div class="loader" style="--mainColor:{mainColor}" />

<style>
  .loader {
    height: 48px;
    width: 48px;
    color: var(--mainColor);
    display: inline-block;
    position: relative;
    border: 3px solid;
    border-radius: 50%;
    border-top-color: transparent;
    border-left-color: transparent;
    transform: rotate(45deg);
    animation: tilt-half-circle 2s linear infinite;
  }

  .loader::before,
  .loader::after {
    content: '';
    height: 0;
    width: 0%;
    color: inherit;
    border-radius: 50%;
    border: 7px solid;
    display: block;
    position: absolute;
  }
  .loader::before {
    left: 25px;
    bottom: 1px;
    animation: move-circle-left 2s linear infinite;
  }
  .loader::after {
    right: 5px;
    bottom: 5px;
    animation: move-circle-right 2s linear infinite;
  }

  @keyframes move-circle-left {
    0%,
    100% {
      left: 5px;
      bottom: 5px;
    }
    20%,
    85% {
      left: 15px;
      bottom: 0px;
    }
    35%,
    70% {
      left: 30px;
      bottom: 7px;
    }
  }

  @keyframes move-circle-right {
    0%,
    20%,
    100% {
      right: 5px;
      bottom: 5px;
    }
    40%,
    80% {
      right: 0px;
      bottom: 15px;
    }
    50% {
      right: 5px;
      bottom: 30px;
    }
  }

  @keyframes tilt-half-circle {
    0%,
    50%,
    100% {
      transform: rotate(45deg);
    }
    25% {
      transform: rotate(15deg);
    }
    75% {
      transform: rotate(75deg);
    }
  }
</style>
