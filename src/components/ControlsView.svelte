<script type="ts">
  import type { RelativeDirection } from '../lib/geometry';

  export let navigate: (relativeDirection: RelativeDirection) => Promise<void>;
</script>

<div class="container">
  <button class="arrow up" on:click={navigate('forward')}>
    ↑
  </button>
  <button class="arrow down" on:click={navigate('backward')}>
    ↓
  </button>
  <button class="arrow left" on:click={navigate('left')}>
    ←
  </button>
  <button class="arrow right" on:click={navigate('right')}>
    →
  </button>
</div>

<style>
  .container {
    border: 1px solid black;
    border-radius: 100%;
    position: absolute;
    right: 20px;
    bottom: 20px;
    width: 64px;
    height: 64px;
    background-color: #d0d0d0;
    opacity: 0.75;
  }

  .arrow {
    position: absolute;
    transform: translate3d(-50%, -50%, 0);
    font-size: 16px;
    font-weight: bold;
    border: none;
    border-radius: 100%;
    background: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 37.5%;
    height: 37.5%;
    user-select: none;
    touch-action: manipulation;
  }
  
  .arrow:hover {
    background-color: #f0f0f0;
  }
  
  .arrow:active {
    background-color: #ffffff;
  }

  .up {
    top: 25%;
    left: 50%;
  }

  .down {
    top: 75%;
    left: 50%;
  }

  .left {
    top: 50%;
    left: 25%;
  }

  .right {
    top: 50%;
    left: 75%;
  }

  @media (max-width: 767px) {
    .container {
      width: 96px;
      height: 96px;
    }
    .arrow {
      font-size: 36px;
    }
    .arrow:hover:not(:active) {
      background-color: initial;
    }
  }
</style>
