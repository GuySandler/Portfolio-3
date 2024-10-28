<script lang="ts">
    import { goto } from '$app/navigation';
    import Button from './button.svelte';

    function GoToPage(page: string) {
        goto("/" + page);
    }
</script>

<div id="navbar">
    <div style="order:1;margin-left:20px;">
        <h3>Guy Sandler</h3>
    </div>
    <div style="order:2;display:flex;justify-content:space-between;align-items:center;">
        <div class="item"><Button Class="hover1" onClick={() => GoToPage("")}>About</Button></div>
        <div class="spacer"></div>
        <div class="item"><Button Class="hover1" onClick={() => GoToPage("skills")}>Skills</Button></div>
    </div>
    <div style="order:3;margin-right: 20px;">
        <h3>Placeholder</h3>
        <!-- placeholder for other stuff -->
    </div>
</div>

<style>
    #navbar {
        display: flex;
        justify-content: space-between;
        align-items: center;

        box-sizing: border-box;
        background-color: #121211;

        color: var(--text);
        font-size: 1.5rem;

        height: 75px;
        width: 100vw;
        margin:0;
        padding:0;

        /* border:1px red solid; */
    }
    .spacer {
        margin-left: 5px;
        display: inline-block;
        margin-right: 5px;
    }
    h3 {
        color: var(--primary);
        text-wrap: none;
        font-size: 2vw;
    }
</style>