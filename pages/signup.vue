<script setup>
import * as yup from "yup";
import { number } from "yup/lib/locale";
definePageMeta({
  layout: "log-in",
});
var isVerify = ref(false);
const isPhone = ref("la");
let phoneschema = yup.object().shape({
  phone: yup.string(),
});

const Singup = reactive({
  chanel: "WEB",
  mobile: "",
  ctype: "MOBILE",
});

const handleSubmit = () => {
  isVerify.value = true;
};
</script>
<template>
  <div>
    <div
      class="
        absolute
        top-0
        left-0
        bg-gradient-to-b
        bottom-0
        leading-5
        h-full
        w-full
        overflow-hidden
      "
    ></div>
    <div
      class="
        relative
        min-h-screen
        sm:flex sm:flex-row
        justify-center
        bg-transparent
        rounded-3xl
        shadow-xl
      "
    >
      <div class="flex justify-center self-center z-10">
        <OtpVerify v-if="isVerify" />
        <div class="p-8 bg-white mx-auto rounded-3xl w-96" v-if="!isVerify">
          <div class="mb-7">
            <h3 class="font-semibold text-2xl text-gray-800">signup</h3>
          </div>
          <div class="space-y-6">
            <div>
              <label>
                <input
                  type="radio"
                  class="px-3"
                  v-model="Singup.ctype"
                  name="typelogin"
                  value="MOBILE"
                />
                Mobile
              </label>
              <label>
                <input
                  type="radio"
                  class="px-3"
                  name="typelogin"
                  v-model="Singup.ctype"
                  value="EMAIL"
                />
                email
              </label>
            </div>
            <div class="">
              <select v-model="isPhone" id="" v-if="Singup.ctype != 'EMAIL'">
                <option value="la">+856</option>
              </select>
              <input
                class="
                  w-full
                  text-sm
                  px-4
                  py-3
                  bg-gray-200
                  focus:bg-gray-100
                  border border-gray-200
                  rounded-lg
                  focus:outline-none focus:border-purple-400
                "
                :type="Singup.ctype != 'EMAIL' ? 'number' : 'email'"
                v-model="phoneschema"
                placeholder=""
              />
            </div>
            <div>
              <button
                type="submit"
                class="
                  w-full
                  flex
                  justify-center
                  bg-purple-800
                  hover:bg-purple-700
                  text-gray-100
                  p-3
                  rounded-lg
                  tracking-wide
                  font-semibold
                  cursor-pointer
                  transition
                  ease-in
                  duration-500
                "
                @click="handleSubmit"
              >
                signup
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>