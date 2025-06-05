<script lang="ts">
    let { text, onclick }:
    {
        text: string
        onclick: (e: MouseEvent) => void | null | undefined;
    } = $props()
</script>

<main>
    <button {onclick}>{text}</button>
</main>

<style>
    @import '../shared.css';

    button {
        background-color: var(--color-button-primary);
        color: var(--color-button-primary-text);
        border-radius: var(--border-radius-full);
        padding: 6px 16px;
        border: none;
        cursor: pointer;
        transition: background-color 0.2s ease-in-out;
        
        &:hover {
            background-color: var(--color-blue-400);
        }
    }
</style>