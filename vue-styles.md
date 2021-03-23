## WEB APP VUE STYLE

### 名称的写法

- UpperCamelCase / PascalCase
  所有单词首字符都大写

- lowerCamelCase / camelCase
  第一个单词首字母小写，其余单词首字母都大写

- kebab-case
  短横线分隔命名

#### 定义组件的名称

定义组件时使用 UpperCamelCase 命名，`MyComponentName`，在使用组件时用`<MyComponentName></MyComponentName>`。

> 尽管直接在 DOM（非模版）中使用使用时只有 kebab-case 有效，`<my-component-name></my-component-name>`

但是，在工程化项目中所有场景都在模版下，UpperCamelCase 的优势就会显现出来

- 自定义组件显示明了
- 组件搜索方便快捷

### 定义组件文件的名称

定义组件文件的名称与定义组件的名称相同，使用 PascalCase

#### 定义事件名称

事件名不会被作为一个 JavaScript 变量名或 property 名，所以没有理由使用 camelCase 或 PascalCase
并且`v-on`事件监听器在 DOM 模版中会被自动转换为全小写（因为 HTML 是大小写不敏感的），所以`v-on:myEvent`
将会变成`v-on:myevent`--导致`myEvent`不可能被监听到

因此，推荐始终使用 kebab-case 的事件名

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
