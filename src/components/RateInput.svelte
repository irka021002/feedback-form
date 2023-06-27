<script>
    import {createEventDispatcher} from "svelte"
    let dispatch = createEventDispatcher()
    let selected = 0
    const handleClick = (rating) => {
        selected = Number(rating)
        dispatch("select-rating", selected)
    }
</script>

<div
    class="mx-10 mt-8 w-full"
>
    <div
        class="flex justify-between"
    >
        <label
            for="rating1"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 1 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="1" id="rating1">
            1
        </label>
        <label
            for="rating2"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 2 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="2" id="rating2">
            2
        </label>
        <label
            for="rating3"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 3 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="3" id="rating3">
            3
        </label>
        <label
            for="rating4"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 4 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="4" id="rating4">
            4
        </label>
        <label
            for="rating5"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 5 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="5" id="rating5">
            5
        </label>
        <label
            for="rating6"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 6 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="6" id="rating6">
            6
        </label>
        <label
            for="rating7"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 7 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="7" id="rating7">
            7
        </label>
        <label
            for="rating8"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 8 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="8" id="rating8">
            8
        </label>
        <label
            for="rating9"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 9 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="9" id="rating9">
            9
        </label>
        <label
            for="rating10"
            class={`hover:bg-pink hover:text-white cursor-pointer w-10 h-10 flex justify-center items-center rounded-full ${selected === 10 ? "bg-pink text-white" : "bg-[#fff0ff]"}`}
        >
            <input class="hidden" type="checkbox" name="rating" on:change={(e) => handleClick(e.currentTarget.value)} value="10" id="rating10">
            10
        </label>
    </div>
    <div
        class="flex justify-between text-base font-semibold mt-2"
    >
        <p>Not likely at all</p>
        <p>Extremely likely</p>
    </div>
</div>