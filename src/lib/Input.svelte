<script lang="ts">
    let { name, placeholder, label, type }:
    {   
        name: string, 
        placeholder: string,
        label: string, 
        type: string 
    } = $props();

</script>

<main>
    <label>
        {label}
        <input {placeholder} {type} {name} id={name} />
    </label>
</main>

<style>
    @import '../shared.css';

    label {
        display: flex;
        flex-direction: column;
        gap: 4px;
        color: var(--color-text-primary);
        min-width: 256px;
        width: fit-content;
    }

    input {
        padding: 8px 12px;
        border-radius: var(--border-radius-12);
        border: 1px solid var(--color-border-primary);
        transition: border-color 0.2s ease-in-out;

        &::placeholder {
            color: var(--color-text-secondary);
        }

        &:hover {
            border-color: var(--color-border-hover);
        }

        &:active, &:focus {
            outline: none;
            border-color: var(--color-border-active);
        }
    }
</style>