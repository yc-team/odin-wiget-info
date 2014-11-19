> 全文注释：

* co-* core组件
* bn-* 业务组件

## co-loading

loading效果支持，支持全局和局部的配置

#### 使用方式：

1、全局方式：

```html
<co-loading></co-loading>
```

2、局部方式：

> 局部loading的化只要给父元素增加

```html
<div style="position:relative">
    <co-loading></co-loading>
</div>
```

注释：

> 它是一个元素调用方式的指令(E)

## bn-crumb

属性 | 含义
------------ | -------------
title    | 一级导航的显示文案
sub-title | 二级导航的显示文案
link      | 一级导航的链接地址

#### 使用方式：

1、不带link的

> 如果不定义link，那一级导航也是一个span元素

```html
<bn-crumb title="proxy" sub-title="home"></bn-crumb>
```

2、带link的：

```html
<bn-crumb link="./admin/proxy" title="proxy" sub-title="home"></bn-crumb>
```


## bn-list

属性 | 含义
------------ | -------------
title        | {String} '列表上面navbar的名称'
add-btn-text | {String} '列表上面navbar右侧的添加操作的按钮名称'
resource-url | {String}
grid-options | {Object}

#### 使用方式：

```html
<bn-list title="proxy配置列表" add-btn-text="增加新配置" 
resource-url="/api/admin/:field" resource-index="name" 
grid-options="gridOptions" batch-options="batchOptions"></bn-list>
```

grid-options的配置细节：

参数 | 含义
------------ | -------------
multiChoose | {Boolean} 是否开启全选模式
fields | {Array}



fields的配置细节：

参数 | 含义
------------ | -------------
sortable    | {Boolean} 是否开启列头排序
placeholder | {String}  占位提示文本设置
editable    | {Boolean} 是否在编辑和新增状态的弹窗里面编辑，如果定义true值就显示
align       | {String} table里面表头的对其方式
editType    | {String} 支持下面这些值：select、select2、text、textarea、checkbox、radio、password、number、email、url
help        | {String} 提醒性质的文本，放在输入域的旁边，不设置就不显示
validate    | required：是否是必填项目，需要直接对应的errorMsg 举例：{ errorMsg: '请输入名称', value: true }

注释：

#### 如何配置textarea

> 支持配置rows

```js
editType: 'textarea',
rows: 6
```

#### 如何配置select

> 也支持配置placeholder

```js
editType: 'select',
selectOptions: [
    {
        value: 0, text: 'apps'
    },
    {
        value: 1, text: 'videos'
    },
    {
        value: 2, text: 'wallpapers'
    },
    {
        value: 3, text: 'ebooks'
    },
    {
        value: 4, text: '其他'
    }
]
```

#### 如何配置checkbox

```js
editType: 'checkbox',
checkboxOptions: [
    {
        value: 0, text: 'apps'
    },
    {
        value: 1, text: 'videos'
    },
    {
        value: 2, text: 'wallpapers'
    },
    {
        value: 3, text: 'ebooks'
    },
    {
        value: 4, text: '其他'
    }
]
```

#### 如何配置radio

```js
editType: 'radio',
radioOptions: [
    {
        value: 0, text: 'apps'
    },
    {
        value: 1, text: 'videos'
    },
    {
        value: 2, text: 'wallpapers'
    },
    {
        value: 3, text: 'ebooks'
    },
    {
        value: 4, text: '其他'
    }
]
```

3. actions

* batch-options







## co-grid

#### 使用方式：

```html
<co-grid multi-choose="gridOptions.multiChoose" 
fields="gridOptions.fields" grid-data="gridData" 
actions="gridOptions.actions" 
sort="paramObj.sort" sort-by="paramObj.sortBy" 
on-delete-item="deleteData(item, action)" 
on-edit-item="editData(item, action)" 
checked-data="checkedData" 
scheme-url="gridOptions.schemeUrl" 
scheme="gridOptions.scheme"></co-grid>
```


## co-sort




## co-alert

1、coConfirm

只有一个参数：msg 提示的内容

#### 使用方式：

```js
coConfirm('Are you sure to delete it?').then(function () {
    //...
});
```

2、coAlert

只有一个参数：msg 提示的内容


#### 使用方式：

```js
coAlert('alert msg').then(function () {
    //...
});
```

## co-input-tip

属性 | 含义
------------ | -------------
help         | '跟在输入域后面的提示内容'
custom-msg   | '自定义的内容'
validator    | ''
for          | ''

#### 使用方式：

```html
<co-input-tip help="field.help" custom-msg="customMsg[field.field]"
validator="field.validate" for="field.field"></co-input-tip>
```



## bn-form

属性 | 含义
------------ | -------------
fields    | ''
datasource    | ''
is-valid    | ''
custom-msg    | ''
on-success    | ''
on-cancel    | ''

#### 使用方式：


```html
<bn-form fields="fields" datasource="formData" is-valid="isValid" 
custom-msg="errorInfo" on-success="ok(data)" on-cancel="cancel()">
</bn-form>
```


