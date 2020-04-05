---
title: 12 vue best-practise for better code
date: 2020-04-05 20:00:39
tags:
---

## Luôn dùng :key bên trong v-for

Sử dụng thuộc tính :key với v-for giúp ứng dụng ổn định và có thể dự đoán được bất cứ khi nào chúng ta muốn thao tác dữ liệu.
Điều này giúp Vue có thể theo dõi trạng thái của các item cũng như có một tham chiếu liên tục đến các thành phần. Một ví dụ trong đó các :key cực kỳ hữu ích là khi sử dụng hình động Animation hoặc Vue transitions.
Không có key, Vue sẽ chỉ cố gắng làm cho DOM hiệu quả nhất có thể. Điều này có thể có nghĩa là các yếu tố trong v-for có thể xuất hiện không theo thứ tự hoặc hành vi mà chúng ta mong muốn, cũng như khó dự đoán hơn. Nếu chúng ta có một tham chiếu khóa duy nhất cho từng thành phần, thì chúng ta có thể dự đoán tốt hơn cách ứng dụng Vue của chúng ta sẽ xử lý thao tác DOM.

```
<!-- BAD -->
<div v-for='product in products'>  </div>

<!-- GOOD! -->
<div v-for='product in products' :key='product.id'>
```

<!--more -->
## Dùng kebab cho các Event

Sử dụng kebab cho các sự kiện custom. 
```
this.$emit('close-window')
// then in the parent
<popup-window @close-window='handleEvent()' />
```

## Khai báo Props với camelCase, và dùng Kebab Case trong các template

Best practise này là do thống nhất với cú pháp của 2 ngôn ngữ html và javascript. Trong javascript thì camelCase là chuẩn còn trong html thì là kebab.
```
BAD!
<PopupWindow titleText='hello world' /> 
props: { 'title-text': String }

GOOD!
<PopupWindow title-text='hello world' /> 
props: { titleText: String }
```

## Data luôn luôn trả về function

Khi để trả về object thì data sẽ được share trong tất cả các instance của component này. Tuy nhiên mục đích luôn là tạo ra các component tái sử dụng được (reusable) do đó nên trả về function trong đó có chưa object data.

```
BAD!
data: {
  name: 'My Window',
  articles: []
}

GOOD!
data () {
  return {
    name: 'My Window',
    articles: []
  }
}
```

## Không dùng v-if với các yếu tố của v-for

Thông thường đôi khi chúng ta sẽ code cả v-if bên trong v-for như dưới.

```
BAD!
<div v-for='product in products' v-if='product.price < 500'>
```

Reference: https://medium.com/js-dojo/vuejs-tips-best-practices-39d9962bb255