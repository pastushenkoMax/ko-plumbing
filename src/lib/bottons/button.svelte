<script>
    export let props
</script>

<button onclick={props.onClick ? props.onClick() : null} style:--width={props.width || "20rem"} type={props.type ? "submit" : null}><img src={props.icon} class="icon" alt="icon" />{props.text}</button>

<style>
    button{
        width: var(--width);
        height: 3rem;
        background: var(--secondery-clr);
        box-shadow: 2px 2px 14.6px rgba(0, 0, 0, 0.25);
        border-radius: var(--border-rad);
        backdrop-filter: blur(10px);
        font-weight: 900;
        display: flex;
        align-items: center;
        text-align: center;
        justify-content: center;
        gap: var(--gap-md);
        color: #FFFFFF;
        line-height: 23px;
        letter-spacing: 0.08em;
        font-size: 1.25rem;
        border: none;
        transition: all 0.3s;
    }
    button:hover{
        cursor: pointer;
        filter: brightness(110%);
    }
</style>