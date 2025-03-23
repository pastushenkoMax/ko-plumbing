<script>
    export let props
    function click(){
        if(props.onClick){
            props.onClick(props.id)
        }
    }
</script>

<button onclick={click} class={props.class || ""}>
    {#if props.img}
        <img src={props.img} alt="img"/>
    {/if}
    {props.text}
</button>

<style>
    .btn-with-bg{
        background-color: #51a3e148;
        background-color: #f663328e;
        font-weight: 900;
        padding: var(--gap-sm) var(--gap-md);
        border-radius: var(--border-rad);
    }

    .btn-with-img{
        display: flex;
        align-items: center;
        gap: var(--gap-sm);
    }

    button{
        border: none;
        background-color: transparent;
        letter-spacing: 0.3em;
        font-weight: 600;
        transition: all 0.3s;
    }

    .active{
        color: var(--accent-clr);
        --underline_clr: var(--accent-clr);
    }

    button:hover{
        cursor: pointer;
        color: #000;
    }

    .link{
        /* margin-top: var(--gap-md); */
        color: var(--secondery-clr);
        filter: brightness(80%);
        transition: all 0.3s;
        letter-spacing: normal;
        letter-spacing: 0.05em;
        text-decoration: underline;
        text-align: left;
        font-size: calc(var(--font-sm) - 4px);

    }

    .link:hover{
        filter: brightness(100%);
    }   

    .btn-with-padding{
        padding: calc(var(--gap-sm) + (var(--gap-sm) / 2) ) var(--gap-md);
        display: flex;
        align-items: center;
        gap: var(--gap-sm);

    }

    .btn-with-padding img{
        width: 18px;
    }

    .btn-with-padding:hover{
        /* background-color: #5289ff49; */
    }
</style>