<script lang="ts">
    let {
        onClick = function() {alert("blank button")},
        Class = "default",
    } = $props();
</script>
<!-- Classes: default, hover1 -->
    <!-- <button onclick={onClick}>{text}</button> -->
    <button onclick={onClick} class={Class}>
        <span><slot/></span>
    </button>
<style>
    button span {
        position: relative;
        z-index: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .hover1 {
        /* border: 3px solid var(--primary); */
        background-color: transparent; /* og color */
        color: var(--primary);
        font-size: 1rem;
        cursor: pointer;
        border-radius: 7px;
        padding: 10px 20px;
        position: relative;
        overflow: hidden;
        transition: color 0.2s ease-in-out, scale 0.2s ease-in-out;
    }
    .hover1::before {
        content: '';
        position: absolute;
        bottom: -50%;
        left: 50%;
        width: 0;
        height: 0;
        background: #505050; /* after color */
        transition: width 0.3s ease-in-out, height 0.3s ease-in-out, transform 0.3s ease-in-out;
        border-radius: 50%;
        z-index: 0;
        transform: translateX(-50%);
    }
    .hover1:hover::before {
        width: 20vw; /* Set a fixed size for the circle */
        height: 20vw;
        transform: translate(-50%, 50%);

    }
    .hover1:hover {
        color: white;
        scale: 1.05;
    }
    .hover1:active {
        scale: 1;
    }

    .default {
        background-color: var(--primary);
        color: var(--text);
        font-size: 1rem;
        cursor: pointer;
        border-radius: 7px;
        transition: scale 0.2s ease-in-out;
        width:100%;
        height:100%;
        border:none;
    }
    .default:hover {
        scale: 1.1;
    }
</style>