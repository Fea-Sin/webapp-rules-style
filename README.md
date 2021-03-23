
## WEB APP STYLE

### 定义组件文件的名称

定义组件文件的名称与定义组件的名称相同，使用PascalCase

#### 定义事件名称

事件名不会被作为一个JavaScript变量名或property名，所以没有理由使用camelCase或PascalCase
并且`v-on`事件监听器在DOM模版中会被自动转换为全小写（因为HTML是大小写不敏感的），所以`v-on:myEvent`
将会变成`v-on:myevent`--导致`myEvent`不可能被监听到

因此，推荐始终使用kebab-case的事件名

### Prop名称

Prop是父组件传给子组件的属性（property），这些property的名称和值分别是prop各自的名称和类型，
JavaScript对象属性名称一般使用camelCase（驼峰命名法）形式
> 在HTML中使用时，camelCase的prop名需要使用其等价的kebab-case（短横线命名法）命名
> 但在工程化项目中都是使用template模版，因此推荐使用camelCase形式

工程化项目
```
<template>
  {{myPropName}}
</template>
<script lang="ts">
@Prop() private myPropName: string
</script>
```
在HTML中使用
```
<component my-prop-name="hello"></component>
```
