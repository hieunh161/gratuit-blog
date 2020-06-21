---
title: Vue coding convention
date: 2020-04-05 20:00:39
category: software
tags:
  - clean-code
  - tips
---

## 1. Đặt tên component dùng nhiều từ

Tên component nên dùng hai từ (đơn) trở lên, ngoại trừ component gốc. Việc này giúp tránh xung đột với các phần tử HTML hiện tại và tương lai, vì tất cả các phần tử HTML đều là từ đơn.

```javascript
// BAD
Vue.component('todo', {
  // ...
})

export default {
  name: 'Todo',
  // ...
}
```

```javascript
// GOOD
Vue.component('todo-item', {
  // ...
})

export default {
  name: 'TodoItem',
  // ...
}
```
<!--more -->
### 2. data trong component - trả về function

Khi dùng thuộc tính data trong một component (nghĩa là ở bất cứ đâu trừ new Vue), giá trị của nó phải là một hàm trả về một object.

```javascript
// BAD
Vue.component('some-comp', {
  data: {
    foo: 'bar'
  }
})

export default {
  data: {
    foo: 'bar'
  }
}
```

```javascript
// GOOD
Vue.component('some-comp', {
  data: function () {
    return {
      foo: 'bar'
    }
  }
})

export default {
  data () {
    return {
      foo: 'bar'
    }
  }
}

// Với đối tượng Vue gốc, bạn có thể dùng object,
// vì chỉ có một đối tượng như thế này trong toàn bộ app.
new Vue({
  data: {
    foo: 'bar'
  }
})
```

### 3. Định nghĩa cho prop càng chi tiết càng tốt

Trong code được commit, định nghĩa cho prop nên chi tiết đến mức có thể. Ít nhất bạn phải chỉ định kiểu dữ liệu của prop. Định nghĩa prop chi tiết có hai lợi ích:

- API của component được document, giúp hiểu dễ dàng hơn về cách dùng component.

- Khi code ở chế độ development, Vue sẽ cảnh báo nếu prop được truyền vào không đúng định dạng, giúp bạn phát hiện các lỗi có thể xảy ra.


```javascript
// BAD
// Như thế này chỉ OK khi viết prototype
props: ['status']
```

```javascript
// GOOD
props: {
  status: String
}

// Càng tốt hơn! 
props: {
  status: {
    type: String,
    required: true,
    validator: function (value) {
      return [
        'syncing',
        'synced',
        'version-conflict',
        'error'
      ].indexOf(value) !== -1
    }
  }
}
```

### 4. Luôn dùng :key bên trong v-for

Sử dụng thuộc tính :key với v-for giúp ứng dụng ổn định và có thể dự đoán được bất cứ khi nào chúng ta muốn thao tác dữ liệu.
Điều này giúp Vue có thể theo dõi trạng thái của các item cũng như có một tham chiếu liên tục đến các thành phần. Một ví dụ trong đó các :key cực kỳ hữu ích là khi sử dụng hình động Animation hoặc Vue transitions.

Không có key, Vue sẽ chỉ cố gắng làm cho DOM hiệu quả nhất có thể. Điều này có thể có nghĩa là các yếu tố trong v-for có thể xuất hiện không theo thứ tự hoặc hành vi mà chúng ta mong muốn, cũng như khó dự đoán hơn. Nếu chúng ta có một tham chiếu khóa duy nhất cho từng thành phần, thì chúng ta có thể dự đoán tốt hơn cách ứng dụng Vue của chúng ta sẽ xử lý thao tác DOM.

```html
<!-- BAD -->
<div v-for='product in products'>  </div>

<!-- GOOD -->
<div v-for='product in products' :key='product.id'>
```
### 5. Tránh dùng v-if chung với v-for

Đừng bao giờ dùng v-if trên cùng một phần tử với v-for.

Có hai trường hợp thường gặp mà chúng ta có xu hướng làm như vậy:

- Để lọc các item từ một danh sách (ví dụ v-for="user in users" v-if="user.isActive"). Trong những trường hợp này, hãy thay thế users bằng một computed property trả về danh sách đã được lọc (ví dụ activeUsers).

- Để tránh hiển thị một danh sách mà ta muốn giấu (ví dụ v-for="user in users" v-if="shouldShowUsers"). Trong những trường hợp này, hãy chuyển v-if lên một phần tử cha (ví dụ ul, ol).

```html
// BAD
<ul>
  <li
    v-for="user in users"
    v-if="user.isActive"
    :key="user.id"
  >
    {{ user.name }}
  <li>
</ul>

<ul>
  <li
    v-for="user in users"
    v-if="shouldShowUsers"
    :key="user.id"
  >
    {{ user.name }}
  <li>
</ul>
```

```html
// GOOD
<ul>
  <li
    v-for="user in activeUsers"
    :key="user.id"
  >
    {{ user.name }}
  <li>
</ul>

<ul v-if="shouldShowUsers">
  <li
    v-for="user in users"
    :key="user.id"
  >
    {{ user.name }}
  <li>
</ul>
```

### 6. Thiết lập phạm vi cho style của component

Set phạm vi css cho các module bằng thuộc tính scoped

```html
// BAD
<template>
  <button class="btn btn-close">X</button>
</template>

<style>
.btn-close {
  background-color: red;
}
</style>
```

```html
// GOOD
<template>
  <button class="btn btn-close">X</button>
</template>

<!-- Dùng thuộc tính `scoped` -->
<style scoped>
.button {
  border: none;
  border-radius: 2px;
}

.button-close {
  background-color: red;
}
</style>
```


```html
// GOOD
<template>
  <button :class="[$style.button, $style.buttonClose]">X</button>
</template>

<!-- Dùng CSS module -->
<style module>
.button {
  border: none;
  border-radius: 2px;
}

.buttonClose {
  background-color: red;
}
</style>
```

```html
// GOOD
<template>
  <button class="c-Button c-Button--close">X</button>
</template>

<!-- Dùng quy chuẩn BEM -->
<style>
.c-Button {
  border: none;
  border-radius: 2px;
}

.c-Button--close {
  background-color: red;
}
</style>
```

### 7. Đặt tên cho private property

Luôn luôn dùng tiền tố $_ cho các private property trong một plugin, mixin vân vân. Tiếp theo, để tránh xung đột với code của các tác giả thư viện khác, thêm vào một phạm vi được định danh (ví dụ $_tênPluginCủaBạn_).

```javascript
// BAD
var myGreatMixin = {
  methods: {
    update: function () {
    }
  }
}

var myGreatMixin = {
  methods: {
    _update: function () {
    }
  }
}

var myGreatMixin = {
  methods: {
    $update: function () {
    }
  }
}

var myGreatMixin = {
  methods: {
    $_update: function () {
    }
  }
}
```

```js
// GOOD
var myGreatMixin = {
  methods: {
    $_myGreatMixin_update: function () {
    }
  }
}
```

### 8. Các file component

Mỗi component nên nằm trong một file riêng. Việc này giúp bạn mau chóng tìm ra một component khi cần chỉnh sửa hoặc xem lại cách dùng component đó.

```js
// BAD
Vue.component('TodoList', {
  // ...
})

Vue.component('TodoItem', {
  // ...
})
```


```js
// GOOD
components/
|- TodoList.js
|- TodoItem.js

components/
|- TodoList.vue
|- TodoItem.vue
```

### 9. Sử dụng quy chuẩn đặt tên cho file component
Toàn bộ tên của các file component chỉ nên được đặt theo quy chuẩn hoặc là PascalCase hoặc là kebab-case.

PascalCase hoạt động tốt nhất với tính năng tự điền (autocomplete) của các trình soạn thảo, vì nó nhất quán với cách chúng ta tham chiếu đến các component trong JS(X) và template, bất cứ khi nào có thể. Tuy nhiên, vì tên file trộn lẫn cả chữ hoa và chữ thường đôi khi tạo phiền toái trên các hệ thống phân biệt hoa thường, kebab-case cũng hoàn toàn có thể chấp nhận được.

```
// BAD

components/
|- mycomponent.vue

components/
|- myComponent.vue
```

```
// GOOD

components/
|- MyComponent.vue

components/
|- my-component.vue
```

### 10. Tên component nền tảng

Tên của các component nền tảng (base component), chỉ dùng để áp dụng style và convention cho toàn bộ ứng dụng, nên bắt đầu bằng một tiền tố đặc biệt, chẳng hạn như Base, App, hoặc V.

```
// BAD
components/
|- MyButton.vue
|- VueTable.vue
|- Icon.vue
```

```
// GOOD
components/
|- BaseButton.vue
|- BaseTable.vue
|- BaseIcon.vue

components/
|- AppButton.vue
|- AppTable.vue
|- AppIcon.vue

components/
|- VButton.vue
|- VTable.vue
|- VIcon.vue
```

### 11. Tên của các component dạng single-instance

Tên của các component dạng single-instance (chỉ có một đối tượng được khởi tạo trong toàn bộ vòng đời của ứng dụng) nên bắt đầu với mạo từ xác định The, đánh dấu tính chất “một và chỉ một mà thôi.”

Điều này không có nghĩa là một component dạng này chỉ được dùng trên một trang duy nhất, mà là chỉ được dùng một lần mỗi trang. Các component này không bao giờ nhận vào các prop, vì prop là dấu hiệu của một component tái sử dụng lại được.

```
// BAD
components/
|- Heading.vue
|- MySidebar.vue
```

```
// GOOD
components/
|- TheHeading.vue
|- TheSidebar.vue
```

### 12. Tên các component có liên hệ chặt chẽ với nhau
Tên của component con có mối quan hệ khắng khít (tightly coupled) với component cha nên có tiền tố là tên component cha.

Nếu một component chỉ có ý nghĩa trong ngữ cảnh của một component cha, mối quan hệ này nên được thể hiện rõ ràng bằng tên của component đó. Vì cách trình soạn thảo thường sắp xếp file theo thứ tự chữ cái, việc này cũng giúp các file liên quan được gần nhau.

```
// BAD
components/
|- TodoList.vue
|- TodoItem.vue
|- TodoButton.vue

components/
|- SearchSidebar.vue
|- NavigationForSearchSidebar.vue
```

```
// GOOD
components/
|- TodoList.vue
|- TodoListItem.vue
|- TodoListItemButton.vue

components/
|- SearchSidebar.vue
|- SearchSidebarNavigation.vue
```

### 13. Thứ tự từ trong tên của component

Tên của component nên được bắt đầu với những từ cấp cao nhất (thường là chung nhất) và kết thúc bằng những từ mô tả.

```
// BAD
components/
|- ClearSearchButton.vue
|- ExcludeFromSearchInput.vue
|- LaunchOnStartupCheckbox.vue
|- RunSearchButton.vue
|- SearchInput.vue
|- TermsCheckbox.vue
```

```
// GOOD
components/
|- SearchButtonClear.vue
|- SearchButtonRun.vue
|- SearchInputQuery.vue
|- SearchInputExcludeGlob.vue
|- SettingsCheckboxTerms.vue
|- SettingsCheckboxLaunchOnStartup.vue
```


### Reference:

[Vue official guide](https://vi.vuejs.org/v2/style-guide/index.html)
[Medium article](https://medium.com/js-dojo/vuejs-tips-best-practices-39d9962bb255)