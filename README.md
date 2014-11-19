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


## bn-crumb

* title      一级导航的显示文案
* sub-title  二级导航的显示文案
* link       一级导航的链接地址

> 如果不定义link，那一级导航也是一个span元素

#### 使用方式：

```html
<bn-crumb title="proxy" sub-title="home"></bn-crumb>
```


## bn-list

#### 使用方式：

```html
<bn-list title="proxy配置列表" add-btn-text="增加新配置" resource-url="/api/admin/:field" resource-index="name" grid-options="gridOptions" batch-options="batchOptions"></bn-list>
```

配置：

* title
* add-btn-text
* resource-url
* resource-index
* grid-options

1. multiChoose      是否开启全选模式
2. fields

    sortable        是否开启列头排序
    placeholder     占位提示文本设置
    editable: 		是否在编辑和新增状态的弹窗里面编辑，如果定义true值就显示能编辑，如果定义false或者不定义editable这个配置，就不显示不能编辑
    align:          table里面表头的对其方式
    editType:       支持下面这些值：select、select2、text、textarea、checkbox、radio、password、number、email、url
    help: 提醒性质的文本，放在输入域的旁边，不设置就不显示
    validate：
    	required：是否是必填项目，需要直接对应的errorMsg
    	举例：{ errorMsg: '请输入名称', value: true }





注释：

* 配置textarea

> 支持配置rows

```js
editType: 'textarea'
```

* 配置select

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

* 配置checkbox

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

* 配置radio

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
<co-grid multi-choose="gridOptions.multiChoose" fields="gridOptions.fields" grid-data="gridData" actions="gridOptions.actions" sort="paramObj.sort" sort-by="paramObj.sortBy" on-delete-item="deleteData(item, action)" on-edit-item="editData(item, action)" checked-data="checkedData" scheme-url="gridOptions.schemeUrl" scheme="gridOptions.scheme"></co-grid>
```


## co-sort




## co-alert


#### 使用方式：

```js

coConfirm('Are you sure to delete it?').then(function () {
    //...
});

```


## co-input-tip

* help
* errorMsg
* customMsg

#### 使用方式：

```html
<co-input-tip help="field.help" custom-msg="customMsg[field.field]" validator="field.validate" for="field.field"></co-input-tip>
```



## bn-form

#### 使用方式：

* fields
* datasource
* is-valid
* custom-msg
* on-success
* on-cancel

```html
<bn-form fields="fields" datasource="formData" is-valid="isValid" custom-msg="errorInfo" on-success="ok(data)" on-cancel="cancel()"></bn-form>
```


