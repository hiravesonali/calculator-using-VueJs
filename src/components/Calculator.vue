<template>
  <div class="mx-auto overflow-hidden mt-10 shadow-lg mb-2 bg-purple-900 shadow-lg border rounded-lg lg:w-2/6 md:w-3/6 sm:w-4/6">
    <div class="">
      <div class="p-5 text-white text-center text-3xl bg-purple-900"><span class="text-orange-500">Calcu</span>lator</div>
      <div class="pt-16 p-5 pb-0 text-white text-right text-3xl bg-purple-800">{{ current || '00' }}</div>
      <div class="p-5 text-white text-right text-3xl bg-purple-800">= <span class="text-orange-500">{{ equalsTo || '00' }}</span></div>
      
      
 <div class="flex items-stretch bg-purple-900 h-24">
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="percentage" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">%</button>
    </div>
  
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="sign" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">+/-</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="remove" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">Del</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="divide" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">÷</button>
    </div>
</div>
      
<div class="flex items-stretch bg-purple-900 h-24">
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('7')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">7</button>
    </div>
  
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('8')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">8</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('9')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">9</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="multiply" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">×</button>
    </div>
</div>
      
<div class="flex items-stretch bg-purple-900 h-24">
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('4')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">4</button>
    </div>
  
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('5')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">5</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('6')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">6</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="minus" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">-</button>
    </div>
</div>
      
<div class="flex items-stretch bg-purple-900 h-24">
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('1')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">1</button>
    </div>
  
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('2')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">2</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('3')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">3</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="add" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">+</button>
    </div>
</div>
      

<div class="flex items-stretch bg-purple-900 h-24 mb-4">
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="clear" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">C</button>
    </div>
  
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="append('0')" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">0</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="dot" class="rounded-full h-20 w-20 flex items-center bg-purple-800 justify-center shadow-xl border-2 border-purple-700">.</button>
    </div>
   
    <div class="flex-1 px-2 py-2 justify-center flex items-center text-white text-2xl font-semibold">
      <button @click="equal" class="rounded-full h-20 w-20 flex items-center bg-orange-500 justify-center shadow-xl border-2 border-orange-600">=</button>
    </div>
</div>
      
      
  </div>
</div>  
</template>

<script>
export default {
    data() {
      return {
        previous: null,
        current: '',
        operator: null,
        operatorClicked: false,
        equalsTo: '',
      }
    },
    methods: {
      clear() {
        this.current = '';
        this.equalsTo = ''; 
      },
      percentage() {
        this.current = `${parseFloat(this.current) / 100}`
      },
      sign() {
        this.current = this.current.charAt(0) === '-' ?
         this.current.slice(1) : `-${this.current}`;
      },
      remove() {
        this.current = this.current.slice(0, -1);
      }, 
      append(number) {
        if (this.operatorClicked) {
          this.current = '';
          this.operatorClicked = false;
        }
        this.current = `${this.current}${number}`;
      },
      dot() {
        if (this.current.indexOf('.') === -1) {
          this.append('.');
        }
      },
      setPrevious() {
        this.previous = this.current;
        this.operatorClicked = true;
      },
      divide() {
        this.operator = (a, b) => a / b;
        this.setPrevious();
      },
      multiply() {
        this.operator = (a, b) => a * b;
        this.setPrevious();
      },
      minus() {
        this.operator = (a, b) => a - b;
        this.setPrevious();
      },
      add() {
        this.operator = (a, b) => a + b;
        this.setPrevious();
      },
      equal() {
        this.current = `${this.operator(
          parseFloat(this.previous), 
          parseFloat(this.current)
          )}`;
          this.equalsTo = this.current;
          this.previous = null;
      }
    }
}
</script>
