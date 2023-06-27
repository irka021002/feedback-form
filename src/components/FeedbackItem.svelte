<script>
    export let feedback
    import { FeedbackStore } from "../stores/FeedbackStore";
    import {fade,scale} from "svelte/transition"
    const handleDelete = () => {
        FeedbackStore.update(() => $FeedbackStore.filter(v => v.id != feedback.id))
    }
</script>

<div
    class="w-full bg-white rounded-lg px-5 py-5 relative mt-5"
    in:scale
    out:fade
>
    <span
        class="w-8 h-8 bg-pink flex justify-center items-center rounded-full absolute -top-3 -left-3 text-white"
    >
        {feedback.rating}
    </span>
    {feedback.text}
    <button
        class="font-bold absolute top-1 right-2 cursor-pointer"
        on:click={handleDelete}
    >
        X
    </button>
</div>