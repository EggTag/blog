---
layout: 'post'
title: 'Vue 3 မှာ အသစ်ပါဝင်လာသည့် Fragment နဲ့ Teleport'
author: zym
---

Vue 3 မှာ အသစ်ပါဝင်လာတဲ့ အသုံးဝင် fragment နဲ့ teleport တွေ အကြောင်းဖြစ်ပါတယ်။

## 1. Multi-root Component ခေါ် Fragments
Vue 2 မှာ template tag အောက်မှာ tag တခုသာ ရေးလို့ရတော့ ၂ခု ၃ခု ထပ်ပြီးထည့်ရေးချင်သည့်အခါမျိုးမှာ div တွေ ထပ်ငုံပြီးရေးနေရတဲ့ အတွက် နဲနဲ တော့ ကသိသအောက်နိုင်ပါတယ်။ Vue3 မှာ အဲကန့်သတ်ချက်ကို ဖယ်ရှားပေးလိုက်ပြီး template အောက်မှာ parallel child tag တွေတခုမကရေးလို့ရသွားတာပါ။ ကြီးကြီးမားမားမဟုတ်ပေမယ့် သိသာတဲ့ ပြောင်းလဲမှုပါ။

```html
<template>  
    <input :name="first_name">
    <input :name="last_name">
    <custom-submit-button>
</template>
```

### 2. Teleport

Vue 3 မှာ အသစ်ပါလာတာပါ။ ဘယ်အတွက် အသုံးပြုလဲ ဆိုတော့ modal တွေ ရေးတိုင်းမှာ ကျနော် တို့ က vue 2 မှာ နဲနဲ တိုင်ပတ်တတ်ပါတယ်။ modal component တွေ ကို layout မှာတိုက်ရိုက် သွားထည့်ထားပြီးတော့ vuex နဲ့ ဖြစ်ဖြစ် event emit လုပ်ပြီးဖြစ်ဖြစ်ခေါ်ရပါတယ်။ layout မှာ တိုက်ရိုက်မထည့်ရင် modal ပြတဲ့ အခါမှာ တလွဲတွေ ဖြစ်နေလို့ပါ။ တကယ်က modal က တချို့ page မှာ သာပါဝင်ပြီး page တိုင်းမှာ ပါဝင်ဖို့မလိုတာပဲ ဖြစ်ပါတယ်။ အဲတော့ သက်ဆိုင်တဲ့ component နဲ့ တွဲလျက်မရှိပဲ layout မှာ မလိုတဲ့ modal component တွေ စုပုံနေတတ်ပါတယ်။ အဲဒါကို ဖြေရှင်းဖို့ teleport ဆိုတဲ့ feature ကိုထွင်ခဲ့တာပါ။ လိုချင်တဲ့ component တွေ ကို `<teleport>` နဲ့ ထည့်လိုက်ပြီး ကိုယ်ပြချင်တဲ့ element, id နဲ့ class တွေ ကို ထည့်ပြီး ပြခိုင်းလိုက်ရင် ပြတဲ့ အခါမှာ အဲ့ element အောက်မှာ တိုက်ရိုက်သွားပြပေးမှာပါ။

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gOPNvjR" data-user="Vue" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/team/Vue/pen/gOPNvjR">
  Vue 3 Teleport</a> by Vue (<a href="https://codepen.io/team/Vue">@Vue</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br/>
`P.S Vue 3 ရဲ့ official documentation မှ ဥပမာဖြစ်ပါတယ်။`
