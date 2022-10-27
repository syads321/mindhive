<script>
import FormSection from "./components/FormSection.vue";
import FormGroup from "./components/FormGroup.vue";
import InputText from "./components/InputText.vue";
import CheckBox from "./components/CheckBox.vue";
import FormButton from "./components/FormButton.vue";
import DropdownSelect from "./components/DropdownSelect.vue";
export default {
  components: {
    FormSection,
    FormGroup,
    InputText,
    CheckBox,
    FormButton,
    DropdownSelect,
  },
  data() {
    return {
      product: {},
    };
  },
  mounted: async function () {
    const fetchproduct = await fetch("https://fakestoreapi.com/products/3");
    const data = await fetchproduct.json();
    this.product = data;
  },
};
</script>

<template>
  <main>
    <div class="ml-auto mr-auto max-w-[950px] pt-12">
      <div class="flex">
        <div class="w-1/2 md:w-full">
          <div class="flex leading-[29px]">
            <img src="/images/left-arrow.png" class="h-[17px] mr-1 mt-1" />
            <div
              class="rounded-full bg-black w-[29px] h-[29px] text-white text-center pt-0 mr-1 leading-[29px]"
            >
              P
            </div>
            Powdur
          </div>
          <div class="ml-4">
            <div class="mt-5">{{ product?.title }}</div>
            <div class="text-[34px]">${{ product?.price }}</div>
          </div>
          <div class="rounded-sm overflow-hidden mt-10 ml-4 w-[300px] h-[284px">
            <img class="w-full" :src="product?.image" />
          </div>
        </div>
        <div class="w-1/2 md:w-full relative">
          <div class="relative overflow-hidden">
            <div
              class="shadow-lg absolute h-full w-[100px] left-[6px] top-0 w-[108px]"
              style="z-index: -1"
            ></div>
            <div>
              <div class="w-[375px] ml-auto mr-8 bg-white pb-4">
                <FormButton type="button">
                  <div
                    class="flex text-white place-content-center leading-[40px]"
                  >
                    <img
                      class="w-[17px] h-[17px] mr-1 mt-3"
                      src="images/apple.png"
                    />
                    <span class="text-[22px]">Pay</span>
                  </div>
                </FormButton>

                <div class="flex mt-[30px]">
                  <hr
                    class="border-t border-slate-400 border-gray h-[1px] w-1/3 mt-[10px]"
                  />
                  <div class="text-[14px] w-1/3 text-center">
                    Or pay with card
                  </div>
                  <hr
                    class="border-t border-slate-400 border-gray h-[1px] w-1/3 mt-[10px]"
                  />
                </div>
                <div class="mt-[26px]">
                  <FormSection title="Shipping Information">
                    <FormGroup label="Email">
                      <InputText
                        type="email"
                        rounded="rounded-md"
                        border="border"
                        placeholder="Email"
                      />
                    </FormGroup>
                    <FormGroup label="Shipping Address">
                      <DropdownSelect />
                      <InputText
                        type="text"
                        border="border"
                        placeholder="Name"
                      />
                      <InputText
                        type="text"
                        rounded="rounded-b-md"
                        border="border-b border-r border-l"
                        placeholder="Address"
                      />
                      <a href="#" class="text-[12px] text-emerald-500 underline"
                        >Enter address manually</a
                      >
                    </FormGroup>
                  </FormSection>
                  <FormSection title="Payment Details">
                    <FormGroup label="Card Information">
                      <InputText
                        type="text"
                        rounded="rounded-t-md"
                        border="border-t border-b border-r border-l"
                        placeholder="1234 1234 1234 1234"
                      >
                        <div class="flex">
                          <img src="/images/amex.jpeg" class="h-[15px] ml-1" />
                          <img src="/images/visa.jpeg" class="h-[15px] ml-1" />
                          <img
                            src="/images/mastercard.jpeg"
                            class="h-[15px] ml-1"
                          />
                        </div>
                      </InputText>
                      <div class="flex">
                        <InputText
                          type="month"
                          rounded="rounded-bl-md"
                          border="border-l border-b border-r"
                        />
                        <InputText
                          type="text"
                          rounded="rounded-br-md"
                          border="border-r border-b"
                          placeholder="CVV"
                        >
                          <div class="flex">
                            <img
                              src="/images/card-cvv-icon.svg"
                              class="h-[15px] ml-1"
                            />
                          </div>
                        </InputText>
                      </div>
                    </FormGroup>
                    <div class="mt-6 mb-7">
                      <CheckBox title="Billing address same as shipping" />
                    </div>
                  </FormSection>

                  <FormButton type="button">
                    <span class="text-gray-500">Pay ${{ product?.price }}</span>
                  </FormButton>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped></style>
