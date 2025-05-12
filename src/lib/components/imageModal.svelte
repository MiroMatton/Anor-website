<script>
    import { createEventDispatcher } from 'svelte';

    export let src = '';
    export let alt = '';
    export let isOpen = false;
    export let closeModal = () => {};
</script>

{#if isOpen}
    <div class="modal-backdrop" on:click={closeModal}>
            <img src={src} alt={alt} />
            <button class="close-button" on:click={closeModal}>×</button>
    </div>
{/if}

<style>
    .modal-backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    img {
        width: 75%;
        display: block;
        border-radius: var(--borderRadius);
    }

    .close-button {
        position: absolute;
        top: 1rem;
        right: 1rem;
        background: none;
        border: none;
        font-size: 3rem;
        cursor: pointer;
        color: var(--green);
    }
</style>