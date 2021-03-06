# el-sku

[![Build Status](https://badgen.net/travis/leezeehowe/el-sku/master)](https://travis-ci.com/leezeehowe/el-sku)
[![NPM Download](https://badgen.net/npm/dm/@leezeehowe/el-sku)](https://www.npmjs.com/package/@leezeehowe/el-sku)
[![NPM Version](https://badge.fury.io/js/%40leezeehowe%2Fel-sku.svg)](https://www.npmjs.com/package/@leezeehowe/el-sku)
[![NPM License](https://badgen.net/npm/license/@leezeehowe/el-sku)](https://github.com/leezeehowe/el-sku/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/lee/el-sku/pulls)
[![Automated Release Notes by gren](https://img.shields.io/badge/%F0%9F%A4%96-release%20notes-00B2EE.svg)](https://github-tools.github.io/github-release-notes/)

`el-sku` is a `vue` component which can **bring you a useful and editable table containing SKU and other extra custom fields** simply by specification attributes coupled with related values array and some config.

![basic function](https://lee-img-bed.oss-cn-shenzhen.aliyuncs.com/el-sku.png)

[在线示例及 API 文档](https://leezeehowe.github.io/el-sku/)

## Table of Contents

- [Features](#features)
- [Install](#install)
- [Links](#links)
- [License](#license)

## Features

- **easy-to-use**,simply by a array containing specification attributes coupled with related values.

  ```json
  [
    {
      "id": 1,
      "prop": "color",
      "label": "颜色",
      "values": [
        {
          "id": 11,
          "text": "黑色"
        },
        {
          "id": 12,
          "text": "白色"
        }
      ]
    },
    {
      "id": 2,
      "prop": "size",
      "label": "尺寸",
      "values": [
        {
          "id": 21,
          "text": "6.4"
        },
        {
          "id": 22,
          "text": "5.8"
        }
      ]
    }
  ]
  ```

* **custom and editable table**, not just generate SKUS and show them, `el-sku` has the ability to bring you whatever extra field you wanna collect.

  ![](https://lee-img-bed.oss-cn-shenzhen.aliyuncs.com/el-sku-custom-column.png)

  ```javascript
  const customColumns = [
    {
      prop: 'status',
      label: '有效',
      width: 100,
      default: true
    },
    {
      prop: 'album',
      label: '图册',
      width: 150,
      default: ['1.jpg', '2.png']
    },
    {
      prop: 'marketPrice',
      label: '市场价',
      width: 200,
      default: 0
    }
  ]
  ```

- **custom assistance operation**, editing SKU might be taxing, so `el-sku` has some built-in overwritable assistance operations and you can add more simply by a `prop`.

  ![](https://lee-img-bed.oss-cn-shenzhen.aliyuncs.com/el-sku-custom-assistance.png)

```javascript
const customAssistance = [
  {
    name: 'autofillStock',
    label: '自动填充库存',
    prop: 'stock',
    cb: function(tableData, editableRow, event) {
      return tableData.map(_ => {
        if (_.color === '黑色') return 5
      })
    }
  }
]
```

- **v-model is fulfilled**, you can use v-model to sync tabledata real-time.

- There will be more following features...
  - built-in submittal using `Axios`.
  - custom field verifications.
  - custom side operation column.

[⬆ Back to Top](#table-of-contents)

## Install

```
npm i @leezeehowe/el-sku
```

[⬆ Back to Top](#table-of-contents)

## Links

- [api documents](https://leezeehowe.github.io/el-sku/)
- [online sample](https://leezeehowe.github.io/el-sku/)

## License

[MIT](./LICENSE)

[⬆ Back to Top](#table-of-contents)
