<script>
    import Button from "./bottons/button.svelte"
    import Send from "../assets/send.svg"
</script>

<form action="https://formspree.io/f/myzewwyz" method="POST" class="contact-form">
    <section class="form-row">
        <label for="name">Your Name</label>
        <input type="text" id="name" name="name" placeholder="Name" required>
    </section>
    <section class="form-row">
        <label for="email">Your Email</label>
        <input type="email" id="email" name="email" placeholder="Email" required>
    </section>
    <section class="form-row">
        <label for="phone">Your Phone Number</label>
        <input type="tel" id="phone" name="phone" placeholder="Phone" required>
    </section>
    <section class="form-row">
        <label for="message">How can we help you?</label>
        <textarea id="message" name="message" rows="4" placeholder="Discribe your problem." required></textarea>
    </section>
    <section>
        <p class="radio-btn-container-label">Preferred contact method</p>
        <div class="radio-btn-container">
            <div class="radio-btn">
                <input type="radio" class="radio-btn-input" id="radio1" name="contact_method" value="Phone" />
                <label class="radio-btn-label" for="radio1">
                    <div class="checkmark">
                        <span class="checkmark-fill"></span>
                    </div>
                    <span class="radio-label">Phone</span>
                </label>
            </div>
            <div class="radio-btn">
                <input type="radio" class="radio-btn-input" id="radio2" name="contact_method" value="Email" />
                <label class="radio-btn-label" for="radio2">
                    <div class="checkmark">
                        <span class="checkmark-fill"></span>
                    </div>
                    <span class="radio-label">Email</span>
                </label>
            </div>
        </div>
    </section>
    <section class="button-container">
        <Button props={{
            icon: Send,
            text: "Send",
            width:"100%",
            type: "submit"
        }}/>
    </section>
</form>


<style>
    form,
    .form-row{
        display: flex;
        flex-direction: column;
    }

    form{
        gap: var(--gap-md);
        background-color: #ffffff;
    }

    .radio-label,
    label{
        font-weight: 600;
        padding-left: var(--gap-sm);
        font-size: 14px;
        color: black;
        font-weight: 400;
    }

    .form-row{
        gap: var(--gap-sm);
    }

    .button-container{
        margin-top: var(--gap-big);
    }

    textarea,
    input{
        border: 1.5px solid #ecedec;
        border-radius: var(--border-rad);
        height: 48px;
        padding-left: var(--gap-sm);
    }

    textarea:focus,
    input:focus {
        outline: none;
    }

    textarea:focus-within,
    input:focus-within {
        border: 1.5px solid var(--secondery-clr);
    }

    textarea{
        height: 12rem;
        /* box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25); */
        resize: none;
        padding: var(--gap-sm);
    }


    .radio-btn-container {
        display: flex;
        flex-direction: column;
        gap: var(--gap-md);
    }

    .radio-btn-input {
        position: absolute;
        opacity: 0;
        width: 0;
        height: 0;
    }

    .radio-btn-label {
        display: flex;
        align-items: center;
        /* transition: all 0.3s ease; */
        cursor: pointer;
    }

    .checkmark {
        position: relative;
        width: 1.625rem;
        height: 1.625rem;
        overflow: hidden;
        border: 1.5px solid #ecedec;
        border-radius: calc(var(--border-rad) / 2);
        }

    .checkmark-fill {
        position: absolute;
        top: 50%;
        left: 50%;
        width: 1.625rem;
        height: 1.625rem;
        opacity: 0;
        background-color: var(--secondery-clr);
        transform: translate(-50%, -50%);
        transition: all 0.3s ease;
    }

    .checkmark-fill:after {
        content: "";
        position: absolute;
        display: none;
        left: 0.563rem;
        top: 0.313rem;
        width: 0.313rem;
        height: 0.625rem;
        border: solid rgb(255, 255, 255);
        border-width: 0 0.188rem 0.188rem 0;
        z-index: 2;
        transform: rotate(45deg);
    }

    .radio-btn-input:checked + .radio-btn-label .checkmark-fill {
        width: 1.625rem;
        height: 1.625rem;
        opacity: 1;
    }
    .radio-btn-input:checked + .radio-btn-label .checkmark-fill:after {
        display: block;
    }

    .radio-btn-input:checked + .radio-btn-label .checkmark {
        border: none;
    }

    .radio-btn-container-label{
        font-size: calc(var(--font-sm) / 1.15);
        font-weight: 400;
        color:  var(--secondery-fnt-clr);
        margin-left: var(--gap-sm);
        margin-bottom: var(--gap-sm);

    }

</style>

