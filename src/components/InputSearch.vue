<template>
    <div class="flex my-5 items-center justify-center">
            <input type="text" placeholder="Nhập thông tin cần tìm"
                @keyup.enter="submit"
                :value="modelValue"
                @input="updateModelValue"
                class="bg-gray-200 focus:outline-none p-[8px] px-5 rounded-[5px] w-1/2 "
            >
        
        <div>
            <button type="button"
            @click="submit"
            class="bg-green-600 p-[8px] px-5 rounded-[5px] ml-[5px] hover:bg-gray-900 text-white"
            >
            <i class="fas fa-search"></i>
            Tìm kiếm
            </button>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            modelValue: { type: String, default: "" },
        },
        emits: ["submit", "update:modelValue"],
        methods: {
            updateModelValue(e) {
                this.$emit("update:modelValue", e.target.value);
            },
            submit() {
                this.$emit("submit");
            },
        },
    };
</script>