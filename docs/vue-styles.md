## VUE STYLE

### 名称的写法

名称的写法一般分为以下三种方式

- UpperCamelCase / PascalCase
  所有单词首字符都大写

- lowerCamelCase / camelCase
  第一个单词首字母小写，其余单词首字母都大写

- kebab-case
  短横线分隔命名

### 定义组件的名称

定义组件时使用 UpperCamelCase 命名，`MyComponentName`，在使用组件时用`<MyComponentName></MyComponentName>`。

> 尽管直接在 DOM（非模版）中使用使用时只有 kebab-case 有效，`<my-component-name></my-component-name>`

但是，在工程化项目中所有场景都在模版下，UpperCamelCase 的优势就会显现出来

- 自定义组件显示明了
- 组件搜索方便快捷

### 定义组件文件的名称

定义组件文件的名称与定义组件的名称相同，使用 PascalCase

### 定义事件名称

`v-on`事件监听器在 DOM 模版中会被自动转换为全小写（因为 HTML 是大小写不敏感的），所以`v-on:myEvent`
将会变成`v-on:myevent`--导致`myEvent`不可能被监听到

vue 官方推荐始终使用 kebab-case 的事件名
但是在 JavaScript 环境中使用 kebab-case 事件名称非常不友好（感觉非常怪异），我们推荐使用 camelCase
举个例子

**camelCase**

```
<MySelect :optionData="optionList" @onSelect="handleSelect"></MySelect>
```

**kebab-case**

```
<MySelect :optionData="optionList" @on-select="handleSelect"></MySelect>
```

### Prop 名称

Prop 是父组件传给子组件的属性（property），这些 property 的名称和值分别是 prop 各自的名称和类型，
JavaScript 对象属性名称一般使用 camelCase（驼峰命名法）形式

> 在 HTML 中使用时，camelCase 的 prop 名需要使用其等价的 kebab-case（短横线命名法）命名
> 但在工程化项目中都是使用 template 模版，因此推荐使用 camelCase 形式

工程化项目

```
<template>
  {{myPropName}}
</template>
<script lang="ts">
@Prop() private myPropName: string
</script>
```

在 HTML 中使用

```
<component my-prop-name="hello"></component>
```

### 定义文件夹的名称

文件夹名称写法，采用 kebab-case 写法

`vue-property`

### 定义文件的名称（非组件文件）

文件的名称采用 kebab-case 写法

`account.ts`、`account-setting.ts`

### css 名称

css 样式名分两种情况

第一种情况是全局样式，通常是在一个单独的样式文件，此时 css 名称采用 kebab-case 写法

```less
// app.less

.main-container {
  width: 100%;
  height: 100%;
}
```

第二种情况是在 Vue 文件中，此时样式一般是作用域样式，此时 css 名称采用 camelCase 写法

```css
.vuBox {
  padding: 20px;
  border: 1px solid green;
}
```
