## `Component.EventHandler` Class



Module: [cc](../modules/cc.md)


Component will register a event to target component's handler.
And it will trigger the handler when a certain event occurs.

!@zh
“EventHandler” 类用来设置场景中的事件回调，
该类允许用户设置回调目标节点，目标组件名，组件方法名，
并可通过 emit 方法调用目标函数。


##### Examples

```js
// Create new EventHandler
var eventHandler = new cc.Component.EventHandler();
eventHandler.target = newTarget;
eventHandler.component = "MainMenu";
eventHandler.handler = "OnClick";
eventHandler.customEventData = "my data";
```

### Index

##### Properties

  - [`target`](#target) `Node` Event target
  - [`component`](#component) `String` Component name
  - [`handler`](#handler) `String` Event handler
  - [`customEventData`](#customeventdata) `String` Custom Event Data



##### Methods

  - [`emitEvents`](#emitevents) 
  - [`emit`](#emit) Emit event with params



### Details


#### Properties


##### target

> Event target

| meta | description |
|------|-------------|
| Type | <a href="../classes/Node.html" class="crosslink">Node</a> |
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:51](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L51) |



##### component

> Component name

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:62](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L62) |



##### handler

> Event handler

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:82](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L82) |



##### customEventData

> Custom Event Data

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:93](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L93) |






<!-- Method Block -->
#### Methods


##### emitEvents



| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:106](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L106) |

###### Parameters
- `events` <a href="../classes/Component.EventHandler.html" class="crosslink">Component.EventHandler[]</a> 
- `params` Any 


##### emit

Emit event with params

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponentEventHandler.js:130](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponentEventHandler.js#L130) |

###### Parameters
- `params` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Array" class="crosslink external" target="_blank">Array</a> 

##### Examples

```js
// Call Function
var eventHandler = new cc.Component.EventHandler();
eventHandler.target = newTarget;
eventHandler.component = "MainMenu";
eventHandler.handler = "OnClick"
eventHandler.emit(["param1", "param2", ....]);
```


