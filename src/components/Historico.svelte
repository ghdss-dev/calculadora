<script lang="ts">
    export let historico: string[];
</script>

<ul class="historico">
    {#each historico as item}
    <li>{item}</li>
    {/each}
</ul>