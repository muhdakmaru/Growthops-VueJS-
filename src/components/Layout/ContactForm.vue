<script setup lang="ts">
import { ref } from 'vue'
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from '@/components/ui/dropdown-menu'
import '/node_modules/flag-icons/css/flag-icons.min.css'

import { Form, Field, ErrorMessage, useForm } from 'vee-validate'
import * as yup from 'yup'

const countryCodes = [
  { label: 'Malaysia +60', value: '+60', flag: 'my' },
  { label: 'Philippines +63', value: '+63', flag: 'ph' },
  { label: 'Hong Kong +852', value: '+852', flag: 'hk' },
  { label: 'Singapore +65', value: '+65', flag: 'sg' },
  { label: 'UAE +971', value: '+971', flag: 'ae' },
]
const selectedCountryCode = ref(countryCodes[0].value)

const schema = yup.object({
  fullname: yup
    .string()
    .required('Full Name is required')
    .min(3, 'Full Name must be at least 5 characters'),
  phone: yup
    .string()
    .required('Phone Number is required')
    .matches(/^[1-9]\d*$/, 'Invalid phone number')
    .min(9, 'Phone Number must be at least 9 digits'),
  email: yup.string().email('Invalid email').required('Email is required'),
  client: yup.string().required('Please select an option'),
  more: yup.string().required('Please write a message'),
  subscribe: yup.boolean().optional(),
  agree: yup
    .boolean()
    .required('You must accept the terms and conditions')
    .oneOf([true], 'You must accept the terms and conditions'),
})

const { handleSubmit } = useForm({
  validationSchema: schema,
  initialValues: {
    agree: false,
    // ...other initial values if needed
  },
})

function onSubmit(values: any) {
  const fullPhone = selectedCountryCode.value + ' ' + values.phone
  const submission = { ...values, phone: fullPhone }
  console.log('Form submitted!', submission)
  alert(JSON.stringify(submission, null, 2))
  // Handle form submission logic here
}
</script>

<template>
  <div class="pt-2 sm:pt-0">
    <div class="flex flex-row justify-center items-start p-10">
      <div class="w-[1200px] sm:w-[1800px] h-auto max-w-none">
        <div class="relative flex flex-col items-start w-full z-10 sm:p-5 pt-8 sm:pt-25">
          <span class="font-extrabold text-[48px] sm:text-[96px] uppercase whitespace-nowrap">
            contact us
          </span>
          <div class="max-w-150">
            <span class="text-[20px] sm:text-[32px] font-medium"
              >Let's create something awesome together</span
            >
          </div>
          <div class="w-full max-w-6xl mt-10">
            <Form :validation-schema="schema" @submit="onSubmit" class="flex flex-col gap-10">
              <!-- Full Name -->
              <div class="flex flex-col">
                <label class="block font-semibold mb-1 text-[#999D9F]" for="fullname"
                  >Full Name</label
                >
                <Field
                  id="fullname"
                  name="fullname"
                  type="text"
                  class="border border-[#666666] rounded-xl px-4 py-2 w-full sm:w-[381px] h-[52px] bg-[#0E1015] focus:border-[#FF3366] focus:outline-none"
                />
                <ErrorMessage name="fullname" class="text-[#FF3366] text-sm" />
              </div>
              <!------------------- Phone Number ---------------->
              <div class="flex flex-col gap-6 sm:flex-row">
                <div>
                  <label class="block font-semibold mb-1 text-[#999D9F]" for="phone"
                    >Phone Number</label
                  >
                  <div
                    class="flex flex-row justify-start border rounded-xl w-full sm:w-[381px] h-[52px] bg-[#0E1015] border-[#F5F5F53D] focus-within:border-[#FF3366]"
                  >
                    <div
                      class="flex flex-row justify-end items-center bg-[#1B1D24] rounded-tl-xl rounded-bl-xl w-[160px] gap-2"
                    >
                      <DropdownMenu>
                        <DropdownMenuTrigger
                          class="text-white flex items-center justify-end w-full h-full px-4 py-2 rounded-tl-xl rounded-bl-xl gap-2 hover:opacity-80 cursor-pointer"
                        >
                          <span class="text-[16px] font-medium">{{ selectedCountryCode }}</span>
                          <img src="@/assets/Icon/arrow-down.svg" alt="phone" class="" />
                        </DropdownMenuTrigger>
                        <DropdownMenuContent class="w-[200px] ml-10 sm:ml-18 mt-0">
                          <DropdownMenuLabel
                            ><span class="font-bold flex flex-row justify-center"
                              >Country Code</span
                            ></DropdownMenuLabel
                          >
                          <DropdownMenuSeparator />
                          <DropdownMenuItem
                            v-for="code in countryCodes"
                            :key="code.value"
                            class="cursor-pointer"
                            @click="selectedCountryCode = code.value"
                          >
                            <span :class="`fi fi-${code.flag}`"></span>

                            <span class="font-semibold">{{ code.label }}</span>
                          </DropdownMenuItem>
                        </DropdownMenuContent>
                      </DropdownMenu>
                    </div>
                    <Field
                      id="phone"
                      name="phone"
                      type="tel"
                      class="p-4 bg-transparent rounded-xl rounded-tl-none rounded-bl-none w-full focus:outline-none focus:ring-0 focus:border-transparent"
                    />
                  </div>
                  <ErrorMessage name="phone" class="text-[#FF3366] text-sm" />
                </div>
                <!---------------------- Work Email ------------------->
                <div class="flex-1 flex flex-col">
                  <label class="block font-semibold mb-1 text-[#999D9F]" for="email"
                    >Work Email</label
                  >
                  <Field
                    id="email"
                    name="email"
                    type="email"
                    class="border rounded-xl border-[#F5F5F53D] px-4 py-2 w-full sm:w-[381px] h-[52px] bg-[#0E1015] focus:border-[#FF3366] focus:outline-none"
                  />
                  <ErrorMessage name="email" class="text-[#FF3366] text-sm" />
                </div>
              </div>
              <!----------- Radio Button Group -------------->
              <div>
                <span class="block font-semibold mb-1 text-[#999D9F]">I want to</span>
                <div class="flex flex-col sm:flex-row gap-5 sm:gap-10">
                  <label class="font-medium flex items-center cursor-pointer">
                    <Field type="radio" name="client" value="become a client" class="hidden peer" />
                    <span
                      class="w-4 h-4 rounded-full border-2 border-[#666666] flex items-center justify-center mr-2 peer-checked:bg-[#33FF85] peer-checked:border-white transition"
                    >
                      <span
                        class="w-2.5 h-2.5 bg-white rounded-full opacity-0 peer-checked:opacity-100 transition"
                      ></span>
                    </span>
                    Become a client
                  </label>
                  <label class="font-medium flex items-center cursor-pointer">
                    <Field type="radio" name="client" value="join the team" class="hidden peer" />
                    <span
                      class="w-4 h-4 rounded-full border-2 border-[#666666] flex items-center justify-center mr-2 peer-checked:bg-[#33FF85] peer-checked:border-white transition"
                    >
                      <span
                        class="w-2.5 h-2.5 bg-white rounded-full opacity-0 peer-checked:opacity-100 transition"
                      ></span>
                    </span>
                    Join the team
                  </label>
                  <label class="font-medium flex items-center cursor-pointer">
                    <Field
                      type="radio"
                      name="client"
                      value="investor enquiry"
                      class="hidden peer"
                    />
                    <span
                      class="w-4 h-4 rounded-full border-2 border-[#666666] flex items-center justify-center mr-2 peer-checked:bg-[#33FF85] peer-checked:border-white transition"
                    >
                      <span
                        class="w-2.5 h-2.5 bg-white rounded-full opacity-0 peer-checked:opacity-100 transition"
                      ></span>
                    </span>
                    Investor enquiry
                  </label>
                  <label class="font-medium flex items-center cursor-pointer">
                    <Field type="radio" name="client" value="others" class="hidden peer" />
                    <span
                      class="w-4 h-4 rounded-full border-2 border-[#666666] flex items-center justify-center mr-2 peer-checked:bg-[#33FF85] peer-checked:border-white transition"
                    >
                      <span
                        class="w-2.5 h-2.5 bg-white rounded-full opacity-0 peer-checked:opacity-100 transition"
                      ></span>
                    </span>
                    Others
                  </label>
                </div>
                <ErrorMessage name="client" class="text-[#FF3366] text-sm" />
              </div>
              <!------------- Tell Us More ------------->
              <div class="flex flex-col">
                <label class="block font-semibold mb-1 text-[#999D9F]" for="more"
                  >Tell us more</label
                >
                <Field
                  as="textarea"
                  id="more"
                  name="more"
                  class="border rounded-xl border-[#F5F5F53D] px-4 py-2 w-full sm:w-[793px] h-[230px] bg-[#0E1015] font-medium pt-5 focus:border-[#FF3366] focus:outline-none"
                  rows="4"
                  placeholder="Briefly describe your message here"
                />
                <ErrorMessage name="more" class="text-[#FF3366] text-sm" />
              </div>
              <!------------- Checkboxes --------------->
              <div class="flex flex-col gap-4">
                <div class="inline-flex items-start">
                  <label class="flex items-center cursor-pointer relative">
                    <Field
                      type="checkbox"
                      name="subscribe"
                      class="peer h-5 w-5 border-2 border-[#666666] cursor-pointer transition-all appearance-none rounded shadow hover:shadow-xl checked:bg-[#33FF85] checked:border-slate-800"
                      id="subscribe"
                      :value="true"
                      :unchecked-value="false"
                    />
                    <span
                      class="absolute text-white opacity-0 peer-checked:opacity-100 top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 pointer-events-none"
                    >
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-3.5 w-3.5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                        stroke="currentColor"
                        stroke-width="1"
                      >
                        <path
                          fill-rule="evenodd"
                          d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                          clip-rule="evenodd"
                        ></path>
                      </svg>
                    </span>
                  </label>
                  <span class="ml-2 text-[#F5F5F5] font-medium"
                    >I want to subscribe to the occasional insightful materials from GrowthOps.
                    (optional)</span
                  >
                </div>
                <div class="inline-flex items-start">
                  <label class="flex items-center cursor-pointer relative">
                    <Field
                      type="checkbox"
                      name="agree"
                      class="peer h-5 w-5 border-2 border-[#666666] cursor-pointer transition-all appearance-none rounded shadow hover:shadow-md checked:bg-[#33FF85] checked:border-slate-800"
                      id="agree"
                      :value="true"
                      :unchecked-value="false"
                    />
                    <span
                      class="absolute text-white opacity-0 peer-checked:opacity-100 top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 pointer-events-none"
                    >
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-3.5 w-3.5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                        stroke="currentColor"
                        stroke-width="1"
                      >
                        <path
                          fill-rule="evenodd"
                          d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                          clip-rule="evenodd"
                        ></path>
                      </svg>
                    </span>
                  </label>
                  <span class="ml-2 text-[#F5F5F5] font-medium"
                    >I have read and agree to the website’s privacy policy.</span
                  >
                </div>
                <ErrorMessage name="agree" class="text-[#FF3366] text-sm" />
              </div>
              <!-- Submit Button -->
              <div class="flex flex-row justify-center sm:justify-start items-center">
                <button
                  type="submit"
                  class="cursor-pointer bg-[#33FF85] hover:bg-[#28cc6a] w-[151px] h-[54px] text-[#F5F5F5] border-1 border-[#F5F5F5] font-bold py-3 px-8 rounded-full mt-4 transition-all duration-200"
                  style="box-shadow: 0px 0px 16px 0px #ff336680"
                >
                  Submit
                </button>
              </div>
            </Form>
          </div>
        </div>
      </div>
    </div>
    <!-- Vector Style Shadow -->
    <div class="relative flex flex-row justify-between items-center">
      <div>
        <img
          src="@/assets/images/vector-contact-left-red.svg"
          alt="Vector Style Shadow"
          class="absolute top-0 left-0 z-0 top-[-990px] sm:top-[-1050px] w-full sm:w-[1200px] h-auto max-w-none"
        />
        <img
          src="@/assets/images/vector-contact-left-red.svg"
          alt="Vector Style Shadow"
          class="sm:hidden absolute top-0 left-0 z-0 top-[-740px] sm:top-[-550px] w-full sm:w-[1200px] h-auto max-w-none"
        />
        <img
          src="@/assets/images/vector-contact-right-red.svg"
          alt="Vector Style Shadow"
          class="sm:hidden absolute top-0 right-0 z-0 top-[-650px] sm:top-[-550px] w-full sm:w-[1200px] h-auto max-w-none"
        />

        <img
          src="@/assets/images/vector-contact-left-cyan.svg"
          alt="Vector Style Shadow"
          class="hidden sm:absolute sm:block left-0 z-0 top-[-420px] sm:w-[700px] h-auto"
        />
      </div>
      <div>
        <img
          src="@/assets/images/vector-contact-right-red.svg"
          alt="Vector Style Shadow"
          class="absolute right-0 z-0 top-[-1500px] sm:top-[-900px] w-auto sm:w-[700px] h-auto"
        />
        <img
          src="@/assets/images/vector-contact-right-cyan.svg"
          alt="Vector Style Shadow"
          class="hidden sm:absolute sm:block top-0 right-0 z-0 top-[-700px] w-auto sm:w-[700px] h-auto"
        />
      </div>
    </div>
  </div>
</template>
