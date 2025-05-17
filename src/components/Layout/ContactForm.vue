<template>
  <div class="pt-15 sm:pt-0">
    <div class="relative flex flex-col items-start w-full pb-30 p-10 z-10 sm:p-20">
      <span class="font-extrabold text-[48px] sm:text-[96px] uppercase"> contact us </span>
      <div class="max-w-150">
        <span class="text-[20px] sm:text-[32px] font-medium"
          >Let's create something awesome together</span
        >
      </div>

      <div class="w-full max-w-6xl mt-10">
        <form class="flex flex-col gap-10">
          <!-- Full Name -->
          <div>
            <label class="block font-semibold mb-1 text-[#999D9F]" for="fullname">Full Name</label>
            <input
              id="fullname"
              type="text"
              class="border border-[#666666] rounded-xl px-4 py-2 w-full sm:w-[381px] h-[52px] bg-[#0E1015] focus:border-[#FF3366] focus:outline-none"
            />
          </div>
          <!-- Phone Number -->
          <div class="flex flex-col gap-6 sm:flex-row">
            <div class="">
              <label class="block font-semibold mb-1 text-[#999D9F]" for="phone"
                >Phone Number</label
              >
              <input
                id="phone"
                type="tel"
                class="border rounded-xl px-4 py-2 w-full sm:w-[381px] h-[52px] bg-[#0E1015]"
              />
            </div>
            <!-- Work Email -->
            <div class="flex-1">
              <label class="block font-semibold mb-1 text-[#999D9F]" for="email">Work Email</label>
              <input
                id="email"
                type="email"
                class="border rounded-xl px-4 py-2 w-full sm:w-[381px] h-[52px] bg-[#0E1015]"
              />
            </div>
          </div>
          <!----------- Radio Button Group -------------->
          <div>
            <span class="block font-semibold mb-1 text-[#999D9F]">I want to</span>
            <div class="flex flex-col sm:flex-row gap-5 sm:gap-10">
              <label class="font-medium flex items-center cursor-pointer">
                <input type="radio" name="client" value="yes" class="hidden peer" />
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
                <input type="radio" name="client" value="no" class="hidden peer" />
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
                <input type="radio" name="client" value="investor" class="hidden peer" />
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
                <input type="radio" name="client" value="others" class="hidden peer" />
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
          </div>
          <!------------- Tell Us More ------------->
          <div>
            <label class="block font-semibold mb-1 text-[#999D9F]" for="more">Tell us more</label>
            <textarea
              id="more"
              class="border rounded-xl px-4 py-2 w-full sm:w-[793px] h-[230px] bg-[#0E1015] font-medium pt-5"
              rows="4"
              placeholder="Briefly describe your message here"
            ></textarea>
          </div>
          <!------------- Checkboxes --------------->
          <div class="flex flex-col gap-4">
            <div class="inline-flex items-start">
              <label class="flex items-center cursor-pointer relative">
                <input
                  type="checkbox"
                  checked
                  class="peer h-5 w-5 border-2 border-[#666666] cursor-pointer transition-all appearance-none rounded shadow hover:shadow-md checked:bg-[#33FF85] checked:border-slate-800"
                  id="check"
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
                <input
                  type="checkbox"
                  checked
                  class="peer h-5 w-5 border-2 border-[#666666] cursor-pointer transition-all appearance-none rounded shadow hover:shadow-md checked:bg-[#33FF85] checked:border-slate-800"
                  id="check"
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
        </form>
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
