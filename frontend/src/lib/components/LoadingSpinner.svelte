<script>
  export let size = 'medium'; // small, medium, large
  export let message = 'Loading...';
</script>

<div class="loading-container" class:small={size === 'small'} class:large={size === 'large'}>
  <div class="spinner-wrapper">
    <div class="spinner"></div>
    <div class="spinner-inner"></div>
  </div>
  {#if message}
    <p class="loading-message">{message}</p>
  {/if}
</div>

<style>
  .loading-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .spinner-wrapper {
    position: relative;
    width: 48px;
    height: 48px;
  }

  .spinner,
  .spinner-inner {
    position: absolute;
    border: 4px solid transparent;
    border-radius: 50%;
    animation: spin 1s linear infinite;
  }

  .spinner {
    width: 100%;
    height: 100%;
    border-top-color: #0d6efd;
  }

  .spinner-inner {
    width: 32px;
    height: 32px;
    top: 8px;
    left: 8px;
    border-top-color: #6c757d;
    animation-duration: 1.5s;
  }

  .loading-message {
    margin-top: 0.75rem;
    font-size: 0.9rem;
    color: #495057;
    font-style: italic;
  }

  .small .spinner-wrapper {
    width: 24px;
    height: 24px;
  }

  .small .spinner-inner {
    width: 16px;
    height: 16px;
    top: 4px;
    left: 4px;
  }

  .large .spinner-wrapper {
    width: 64px;
    height: 64px;
  }

  .large .spinner-inner {
    width: 48px;
    height: 48px;
    top: 8px;
    left: 8px;
  }

  @keyframes spin {
    to {
      transform: rotate(360deg);
    }
  }

  .loading-message {
    margin: 0;
    color: #4a5568;
    font-size: 1rem;
    font-weight: 500;
    letter-spacing: 0.3px;
  }

  .loading-container.small .loading-message {
    font-size: 0.875rem;
  }

  .loading-container.large .loading-message {
    font-size: 1.125rem;
    font-weight: 600;
  }

  @media (max-width: 768px) {
    .loading-container {
      padding: 1.5rem;
      gap: 1rem;
    }

    .loading-container.large {
      padding: 2rem;
    }

    .spinner {
      width: 50px;
      height: 50px;
    }

    .spinner-inner {
      width: 34px;
      height: 34px;
    }

    .loading-message {
      font-size: 0.9rem;
    }
  }
</style>
