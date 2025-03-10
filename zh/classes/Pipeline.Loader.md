## `Pipeline.Loader` 类型



模块: [cc](../modules/cc.md)
父模块: [cc](../modules/cc.md)


The loader pipe, it can load several types of files:
1. Images
2. JSON
3. Plist
4. Audio
5. Font
6. Cocos Creator scene
It will not interfere with items of unknown type.
You can pass custom supported types in the constructor.



### 索引



##### 方法

  - [`constructor`](#constructor) Constructor of Loader, you can pass custom supported types.
  - [`addHandlers`](#addhandlers) Add custom supported types handler or modify existing type handler.



### Details




<!-- Method Block -->
#### 方法


##### constructor

Constructor of Loader, you can pass custom supported types.

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/load-pipeline/loader.js:261](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/load-pipeline/loader.js#L261) |

###### 参数列表
- `extMap` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> Custom supported types with corresponded handler

##### 示例

```js
var loader = new Loader({
   // This will match all url with `.scene` extension or all url with `scene` type
   'scene' : function (url, callback) {}
});
```

##### addHandlers

Add custom supported types handler or modify existing type handler.

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/load-pipeline/loader.js:281](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/load-pipeline/loader.js#L281) |

###### 参数列表
- `extMap` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> Custom supported types with corresponded handler



