<script>
    import RateInput from "./RateInput.svelte";
    import {v4 as uuid4} from "uuid"
    import { FeedbackStore } from "../stores/FeedbackStore";
    let rating = 0
    let text = ""
    let minLength = 10
    let disabled = true
    let message
    const handleSubmit = () => {
        const newFeedback = {
            id: uuid4(),
            text,
            rating
        }
        FeedbackStore.update(() => [newFeedback, ...$FeedbackStore])
        text = ""
        console.log($FeedbackStore)
    }
    const handleRating = (e) => {
        rating = e.detail
        if(rating === 0) {
            message = "You must select rating"
            disabled = true
            return
        }
    }
    const handleLength = () => {
        if(text.trim().length <= minLength) {
            message = "Feedback minimum length is 10 charachter"
            disabled = true
            return
        }
        disabled = false
    }
</script>

<div
    class="bg-white w-full px-10 py-10 mt-20 rounded-lg flex flex-col items-center"
>
    <p
        class="text-center font-semibold font-serif text-2xl max-w-[600px]"
    >
        How likely are you to recommend UI Design Daily to your colleagues?
    </p>
    <RateInput on:select-rating={handleRating} />
    <div    
        class="w-full px-4 py-2 mt-8 border rounded-lg flex justify-between"
    >
        <input class="w-10/12 outline-none" on:change={handleLength} type="text" placeholder="Tell us something that keeps you coming back." bind:value={text} />
        <button
            class="bg-darkBlue text-white rounded-lg py-3 px-5 disabled:bg-gray3"
            {disabled}
            on:click={handleSubmit}
        >
            Send
        </button>
    </div>
    {#if message}
        <p class="mt-3">{message}</p>
    {/if}
</div>