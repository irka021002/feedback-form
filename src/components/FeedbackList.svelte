<script>
    import { FeedbackStore } from "../stores/FeedbackStore";
    import FeedbackItem from "./FeedbackItem.svelte";
</script>

<div
    class="w-full mt-5"
>
    {#each $FeedbackStore as feedback (feedback.id)}
        <FeedbackItem {feedback} />
    {/each}
</div>