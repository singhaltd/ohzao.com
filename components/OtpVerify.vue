<script setup>
import { ref } from "vue";
import * as yup from "yup";
import "@/types/RegisterType";

const initOpt = () => {
  const inputs = document.querySelectorAll("#otp > *[id]");
  for (let i = 0; i < inputs.length; i++) {
    inputs[i].addEventListener("keydown", function (event) {
      if (event.key === "Backspace") {
        inputs[i].value = "";
        if (i !== 0) inputs[i - 1].focus();
      } else {
        if (i === inputs.length - 1 && inputs[i].value !== "") {
          return true;
        } else if (event.keyCode > 47 && event.keyCode < 58) {
          inputs[i].value = event.key;
          if (i !== inputs.length - 1) inputs[i + 1].focus();
          event.preventDefault();
        } else if (event.keyCode > 64 && event.keyCode < 91) {
          inputs[i].value = String.fromCharCode(event.keyCode);
          if (i !== inputs.length - 1) inputs[i + 1].focus();
          event.preventDefault();
        }
      }
    });
  }
};

const isVerified = ref(false);

const handleRegister = ()=> {
    console.log(ReqUserRegister)
}
onMounted(() => {
  initOpt();
});
</script>
<template>
  <div class="w-full">
    <div
      class="bg-white shadow-md h-64 py-3 rounded-3xl text-center"
      v-if="!isVerified"
    >
      <h1 class="text-2xl font-bold">OTP Verification</h1>
      <div class="flex flex-col mt-4">
        <span>Enter the OTP you received at</span>
        <span class="font-bold">+8562055****76</span>
      </div>

      <div id="otp" class="flex flex-row justify-center text-center px-2 mt-5">
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="first"
          maxlength="1"
        />
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="second"
          maxlength="1"
        />
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="third"
          maxlength="1"
        />
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="fourth"
          maxlength="1"
        />
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="fifth"
          maxlength="1"
        />
        <input
          class="m-2 border h-10 w-10 text-center form-control rounded"
          type="text"
          id="sixth"
          maxlength="1"
        />
      </div>

      <div class="flex justify-center text-center mt-5">
        <button
          class="
            flex
            items-center
            text-blue-700
            hover:text-blue-900
            cursor-pointer
          "
          @click="isVerified = true"
        >
          <span class="font-bold">Resend OTP</span
          ><i class="bx bx-caret-right ml-1"></i>
        </button>
      </div>
    </div>
    <section v-if="isVerified" class="p-8 bg-white mx-auto rounded-3xl w-96">
      <div class="mb-7">
        <h3 class="font-semibold text-2xl text-gray-800">signup</h3>
      </div>
      <div class="space-y-6">
        <div
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
        >
          +856
          <input
            class=""
            disabled
            type="text"
            value="2055057246"
            placeholder=""
          />
        </div>
        <div class="">
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
            type="text"
            v-model="ReqUserRegister.firstname"
            placeholder="firstname"
          />
        </div>
        <div class="">
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
            type="text"
            v-model="ReqUserRegister.lastname"
            placeholder="lastname"
          />
        </div>
        <div class="">
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
            type="text"
            v-model="ReqUserRegister.password"
            placeholder="password"
          />
        </div>
        <div class="">
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
            type="text"
            v-model="ReqUserRegister.cpassword"
            placeholder="password_confirmation"
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
    </section>
  </div>
</template>