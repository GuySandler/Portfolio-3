<script lang="ts">
    import Navabar from "$lib/components/navabar.svelte";
    import Button from "$lib/components/button.svelte";

    import Github from "$lib/images/github.svg";
    import Mail from "$lib/images/mail.svg";
    import Linkedin from "$lib/images/linkedin.svg";

    function GoTo(link) {
        // window.location.href = link, '_blank';
        window.open(link, '_blank');
    }
</script>

<nav>
    <Navabar />
</nav>

<main style="height:calc(100% - 75px);">
    <div id="main"><slot /></div>
    <div id="bottomLeft">
        <div class="item"><Button onClick={() => GoTo("https://github.com/GuySandler")}><img alt="Github" src={Github}></Button></div>
        <div class="item"><Button onClick={() => GoTo("mailto:guy@sandler.co.il")}><img alt="Email" src={Mail}></Button></div>
        <div class="item"><Button onClick={() => GoTo("https://www.linkedin.com/in/guy-sandler-10197b281/")}><img alt="Linkedin" src={Linkedin}></Button></div>
    </div>
</main>

<style>
    :root {
        --text: #eeeeee;
        --background: #141414;
        --secondsaryBackground: #28333d;
        --primary: #23a7f3;
        --secondary: #228ba0;
        --accent: #3fd1ee;

        width:100vw;
        height:100vh;
        /* background-color: blue; */
        /* background-size: 40px 40px; */
        background-size: 3vw 3vw;
        background-color: var(--background);
        background-image: radial-gradient(circle, var(--secondsaryBackground) 1px, rgba(0, 0, 0, 0) 1px);
        background-position: center;

        font-family: "ubuntu";
        color: var(--text);
    }
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    #bottomLeft {
        position: absolute;
        bottom: 15px;
        left: 15px;
        width: 50px;
        height: 200px;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        align-content: stretch;
    }
    #bottomLeft div {
        display: block;
        flex-grow: 0;
        flex-shrink: 1;
        flex-basis: auto;
        align-self: auto;
        order: 0;
    }
    .item {
        width:50px;
        height:50px;
    }
    img {
        width:100%;
        aspect-ratio: 1 / 1;
        object-fit: cover;
    }
    #main {
        /* margin: 20px; */
        display: flex;
        justify-content: center;
        align-items: center;
        /* border:1px green solid; */
        height: 100%;
    }
</style>