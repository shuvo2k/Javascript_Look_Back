# জাভাস্ক্রিপ্ট ফিরে দেখা

জাভাস্ক্রিপ্ট একটি ডাইনামিক,ক্রস প্ল্যাটফর্ম, অবজেক্ট-অরিন্টেড,ইন্টারপ্রিটেড, কেস-সেন্সিটিভ  ক্রিপ্টিং ভাষা । যা ওয়েব ব্রউজার এর ভেতরে রান করে । যদিও এখন এর ব্যবহার
ক্লাইন্ট সাইট পেরিয়ে সার্ভার এবং ডেস্কটপ এপ্লিকেশন এও ব্যবহার হছে ।
জাভাস্ক্রিপ্টকে আমরা ECMASCRIPT ও বলে থাকি, যাকে সাধারণত একটি স্ট্যান্ডারাড ধরা হয় জাভাস্ক্রিপ্ট এর । বর্তমানে ES6(ECMASCRIPT6) স্ট্যান্ডারাড ব্যবহার হয়ে থাকে । পূর্বে ES5 ব্যবহার হত, এই দুটি সংস্করণ এর মধ্যে পার্থক্য হল নতুন কিছু ফিচার ES6 এ যোগ হয়েছে এবং কোড লিখা সহজতর ES5 এর তুলনায় । বর্তমানে সকল আধুনিক ওয়েব ব্রউজার ES6 সাপোর্ট করে, তবে যেসব ব্রউজার ES6 সাপোর্ট করেনা তারা বিভিন্ন ধরনের ট্রান্সপাইলার ব্যবহার করে ES6 কে ES5 এ কনভার্ট করার জন্য । ইতিহাস আর ফিচার এর ভেতর অনেক ঘোরাঘুরি হল, এখন দেখা যাক কিভাবে আমরা জাভাস্ক্রিপ্ট ব্যাবহার করতে পারি । 

## ওয়েবপেইজে জাভাস্ক্রিপ্ট এর ব্যাবহার 
### ওয়েব কনসোল
যে কোন ওয়েব ব্রউজার ওপেন করে `Ctrl`+`Shift`+`K`
অথবা *Right click then Inspect* করলেই একটি উইন্ডো ওপেন হব, সেখানে *Console* ট্যাবে ক্লিক করলেই কনসোল ওপেন হবে । এখন এইখানে আমরা এখন জাভাস্ক্রিপ্ট লিখতে পারি :) ।

![console screensot](https://github.com/shuvo2k/Javascript_Look_Back/tree/master/images/console.jpeg)

### এইচটিএমএল ফাইল আলাদা জাভাস্ক্রিপ্ট ফাইল আড করে
এইচটিএমএল ফাইলে আমরা `script` টাগ এর মাধ্যমে জাভাস্ক্রিপ্ট লিখতে পারি অথবা আলাদা জাভাস্ক্রিপ্ট ফাইল `script` টাগ এর `src` অ্যাট্রিবিউট মাধ্যমে যোগ করতে পারি । 
```
<html>
  <head></head>
<body>
  <script>
    alert("hello js");
  </script>
</body>
</html>
```
 
  ```
<html>
  <head></head>
<body>
  <script src="test.js"></script>
</body>
</html>
  
  ```
## কমেন্টিং 
কমেন্টিং সাধারণত কোড রিডেবিলিটি বাড়ায় । জাভাস্ক্রিপ্ট সাধারণত দুই ধরনের কমেন্টিং সাপোট করে(সিঙ্গেল লাইন এবং মাল্টিলাইন কমেন্ট) 
```
//a single line comment
/*
  A multiline comment
*/
/*we can't do that*/nested commenting, it will cause Syntax Error*/
```

## ভেরিয়েবল ডিক্লেয়ারেশন 
জাভাস্ক্রিপ্টে `var`, `let`, `const`  কিওয়ার্ড এর মাধ্যমে আমরা ভেরিয়েবল ডিক্লেয়ার করতে পারি (`let`,`const` ES6 এর নতুন ফিচার যার মাধ্যমে ব্লকলেভেল ভেরিয়েবল ডিক্লেয়ার করা যায় ।)

### `var` এর মাধ্যমে ভেরিয়েবল ডিক্লেয়ারেশন
```
var person1 = "alen";  
//পারসন১ ভেরিয়েবল আমরা চাইলেই আবার ডিক্লেয়ার করতে পারি কোন ইরর ছাড়াই 
var person1 = "modified alen";
//এখন আমাদের পারসন ভেরিয়েবল এর মান কিন্তু "modifed alen"
console.log(person1); 
> "modified person"
```
>`var` মাধ্যমে সাধারণত ব্লকলেভেল ভেরিয়েবল ডিক্লেয়ার করা যায় না, ফাংশন বা অবজেক্ট এর ভেতরে >`var` লোকাল ভেরিয়েবলে হিসেবে কাজ করে, বাইরে গ্লোবাল ভেরিয়েবল হিসেবে কাজ করে উদাহরন স্বরূপ - 
```
var name = "alen";
if(name == "alen"){
  var name = "alen walker";
  console.log(name);
}
//নেম ভেরিয়েবল কিন্তু এখন চেঞ্জড, নতুন করে অ্যাকসেস করতে গেলে নতুন মান পাব । 
console.log(name);
//দেখাযাক ফাংশন এর ভেতর `var` কেমন আচরণ করে 
var global = "inside global";
function testVar(){
  var global = "inside testVar";
  var local = "local function variable";

  console.log(global);
} 

console.log(global);   //"inside global"
test();                //"local function variable
console.log(global);   //"insilde global"
console.log(local);    //will show ReferenceError 
```

>ফাংশনের বা ব্লকলেভেল কোডের ভেরিয়েবল লুকআপ একটা অর্ডার আছে প্রথমত এর কোডব্লকের ভেতরে মানে লোকালি,তারপর যদি না ওই নামের কোন ভেরিয়েবল পাওয়া যায় তাহলে গ্লোবালি খোঁজা হয় । যদি গ্লোবালিও না পাওয়া যায় তাহলে প্রোগ্রাম রেফারেন্স এরর শো করে । একেই সাধারণত ভেরিয়েবল লুকাআপ অর্ডার বলাহয়ে থাকে । আরেক সেন্সে স্কোপিংও বলা যেতে পারে, যেমনটা দেখতে পাই লোকালি খোঁজাকে লোকাল স্কোপিং, গ্লোবাল খোঁজাকে গ্লোবাল স্কোপিং বলা হয়ে থাকে ।


### `let` এর মাধ্যমে ভেরিয়েবল ডিক্লেয়ারেশন

যেহেতু স্কোপিং সমন্ধে একটা আইডিয়া হয়ে গেছে এখন `let` এর মাধ্যমে ভেরিয়েবল ডিক্লেয়ার ব্যাপারটি সহজই মনে হবে । `var` এর সাথে পার্থক্য হল `let` এর মাধ্যমে আমরা ব্লকলেভেল ভেরিয়েবল ডিক্লেয়ার করতে পারি আর একই নামের ডিক্লেয়ার করা ভেরিয়েবল দ্বিতীয়বার ডিক্লেয়ার করতে পারবনা । যদি সামহাউ করে ফেলি উই উইল এন্ড আপ উইথ এরর এরর :smile: । তবে যদি আবার কোন লোকাল স্কোপের ভেতরে এইকাজ করি মানে গ্লোবাল আর লোকাল `let` ভেরিয়েবলের নেম একই হয় তাহলে কিন্তু সমস্যা নাই, কারন তখন লুকআপ,স্কোপের ব্যাপারগুলো চলে আসে । কারণ গ্লোবাল ভেরিয়েবল খুঁজেই পাবে না আর লোকাল ভেরিয়েবল তার লোকাল স্কোপের বাইরেই যেতে হবে না সুতরাং কনফ্লিক্টের সম্ভাবনাই আসেনা । তাহলে কিছু উদাহরন দেখা যাক-
```
let amount = 500;
let amount = 700;  //will throw error because we decleared amount already

if(amount > 400){
  let sign = "ok";
  let amount = 600;
  console.log(amount);
}

//output will be
>600

//if we want to access sign we will get some error because it's inside a block
>sign;
>"ReferenceError"

//if we want to see amount we will see the 500 not the changed amount 600 inside block 
>amount;
>500

//Hope that all make sense 
```
>একইভাবে আমরা ফাংশন এর বাইরে এবং ভেতরে `let` দ্বারা ভেরিয়েবল ডিক্লেয়ার করে এর ক্যারেক্টার বা বিহেভিওর গুলোদেখতে পারি । 
আরও একটি উদাহরণ যদি দেখি `setTimeOut()` ফাংশন ব্যাবহারে কিভাবে `var & let` এর ক্যারেক্টারের চেঞ্জ হয় ।
```
for (var i = 0; i < 7; ++i) {
  setTimeout(function () {
    console.log(i);
    // => 8
    // => 8
    // => 8
    // => 8
    // => 8
    // => 8
    // => 8
    // => 8
  }, 1000);
}

for (let i = 0; i < 7; ++i) {
  setTimeout(function () {
    console.log(i);
    // => 0
    // => 1
    // => 2
    // => 3
    // => 4
    // => 5
    // => 6
    // => 7
  }, 1000);
}

```

###  `const` এর মাধ্যমে ভেরিয়েবল ডিক্লেয়ারেশন
`const` বা কন্সটেন্ট দ্বারা ডিক্লেয়ার করা ভেরিয়েবল এর মান আমরা চেঞ্জ করতে পারি না আথাত শুধুমাত্র রিডঅনলি ভেরিয়েল তৈরি করা যায় । যদি অবজেক্ট ডিক্লেয়ার করি সেক্ষেত্রে প্রোপার্টি যোগ করতে পারব কিন্তু পুরো অবজেক্ট চেঞ্জ করতে গেলে বা অন্য ডাটাটাইপ অ্যাসাইন করতে গেলে এরর এর সম্মুখীন হব । সুতরাং বোঝাই যাচ্ছে `let vs const` এর পার্থক্য হচ্ছে একটা রিডেবল প্লাস রাইটেবল আর আরেকটা হচ্ছে শুধুমাত্র রিডেবল । চলুন উদাহরণসহ দেখা যাক :
```
const PI = 3.142;
const PI = 3.14;   //changing value of const variable will end up with error

const obj = {}     //if the variable is object we can assign property and methods 
obj.name = 'jenny';
obj.getName = function(){
  return this.name;
}

const obj = "string";  //this will also throw error we know why
```

>`const` এর ব্যাবহার আমরা তখনি করব যখন আমারা চাইব যে আমাদের ডিক্লেয়ার করা ভেরিয়েবল এর মান যেন কোনভাবেই চেঞ্জ না হয় । 
> বেসিক্যালি ভেরিয়েবল ডিক্লেয়ার `let` দ্বারাই করা ভাল । ইনকেস যদি এমনটা চাই যে  ভেরিয়েবল এর মান প্রোগ্রামের ভেতর যেন কোনভাবেই চেঞ্জ না হয় তাহলে `const` ইজ বেটার ওয়েটু ডু দিস । 

## ভেরিয়েবল স্কোপিং এবং ভেরিয়েবল হোস্টিং 
আমাদের অলরেডি স্কোপিং সম্বন্ধে জানি যে ভেরিয়েবল যে ব্লকের মধ্যে থাকে সেইটা তার স্কোপ, হতে পারে সেইটা লোকাল অথবা গ্লোবাল স্কোপ । 
আর ভেরিয়েবল হোস্টিং হল যে আমরা ভেরিয়েবল এক্সেস করতে পারি তা ডিক্লেয়ার বা ইনিসিয়ালাইজ করার আগেই এবং কোন এরর ছাড়াই, যদিও আমরা ওই ভেরিয়েবল এর মান  `undefined` বা অনির্দিষ্ট পাব ।
```
//মান সেট বা ডিক্লেয়ার করার আগেই ভেরিয়েবল এক্সেস করতে চাইলে ভেরিয়েবল এর মান undefined দেখব কনসোলে 
console.log(x); //undefined
var x;
x = 3;

var y;
console.log(y); //undefined
y = 4;

//বোঝাই যাচ্ছে যে myvar এখানে গ্লোবাল ভেরিয়েবল 
var myvar = 'my value';
 
 /*
 নিচের ফাংশনটিকে সেলফ ইনভোকিং ফাংশন বলা হয়ে থাকে কারন দেখতেই পাচ্ছি যে নামবিহীন ফাংশনটি প্যারেন্থথেছিস এর ভেতরে ডিক্লেয়ার করার পরপরই আবার প্যারেন্থেছিস এর মাধ্যমে কল করা হয়েছে এই জন্যই এই ফাংশনকে `IIFE -> Immediately Invoking Function Exptession` বলা হয় ।
 প্রবর্তিতে এই ফাংশন সম্পর্কে আমরা আরও জানব । তাছাড়া দেখতে পাচ্ছি myvar ভেরিয়েবলটি undefined কারন আমরা ভেরিয়েবলটি ইনিশিয়ালাইজ করি নাই অর্থাৎ ভেরিয়েবল হোস্টিং রুল ।
 */
 (function() {
  var myvar;
  console.log(myvar); // undefined
  myvar = 'local value';
})();

//> undefined
``` 
> `ES6` বা জাভাস্ক্রিপ্টের নতুন স্পেসিফিকেশানে  `let` এবং `const` দ্বারা যদি ভেরিয়েবল ডিক্লেয়ার করার আগেই এক্সেস করতে চাই তাহলে রেফারেন্স এরর পাব । তবে ভেরিয়েবল ইনিশিয়ালাইজ করার পর মান না সেট করেই এক্সেস করতে চাইলে `undefined` পাব । সহজ কথায় `let & const` দ্বারা ডিক্লেয়ার করা ভেরিয়েবল হোস্টিং রুল ফলো করে না । আর ফলো করতে গেলেই রেফারেন্স এরর দেখব, শুধুমাত্র `var` এই রুল ফলো করে সো কিপ দাট ইন মাইন্ড বিফোর ডিক্লেয়ারিং ভেরিয়েবল । 
```
console.log(myVar);  //ReferenceError
let myVar = "haha";

let myVar2;
console.log(myVar2);  //undefined
```


## কন্ডিশনের মারপ্যাঁচ 

