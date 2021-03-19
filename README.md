
## WEB APP VUE STYLE

### 名称的写法

- UpperCamelCase / PascalCase
所有单词首字符都大写

- lowerCamelCase / camelCase
第一个单词首字母小写，其余单词首字母都大写

- kebab-case
短横线分隔命名

#### 定义组件的名称

定义组件时使用UpperCamelCase命名，`MyComponentName`，在使用组件时用`<MyComponentName></MyComponentName>`。

> 尽管直接在DOM（非模版）中使用使用时只有kebab-case有效，`<my-component-name></my-component-name>`

但是，在工程化项目中所有场景都在模版下，UpperCamelCase的优势就会显现出来
- 自定义组件显示明了
- 组件搜索方便快捷
