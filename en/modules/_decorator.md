
## `_decorator` Module






Some JavaScript decorators which can be accessed with "cc._decorator".





### Index



##### Methods

  - [`ccclass`](#ccclass) Declare the standard [ES6 Class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)...
  - [`property`](#property) Declare property for [CCClass](../../../manual/en/scripting/reference/attributes.html).
  - [`executeInEditMode`](#executeineditmode) Makes a CCClass that inherit from component execute in edit mode.<br>...
  - [`requireComponent`](#requirecomponent) Automatically add required component as a dependency for the CCClass that inherit from component.
  - [`menu`](#menu) The menu path to register a component to the editors "Component" menu.
  - [`executionOrder`](#executionorder) The execution order of lifecycle methods for Component.
  - [`disallowMultiple`](#disallowmultiple) Prevents Component of the same type (or subtype) to be added more than once to a Node.
  - [`playOnFocus`](#playonfocus) If specified, the editor's scene view will keep updating this node in 60 fps when it is selected, otherwise, it will update only if necessary.<br>...
  - [`inspector`](#inspector) Specifying the url of the custom html to draw the component in **Properties**.
  - [`icon`](#icon) Specifying the url of the icon to display in the editor.
  - [`help`](#help) The custom documentation URL.
  - [`mixins`](#mixins) The old mixins implemented in cc.Class(ES5) behaves exact the same as multiple inheritance.



### Details




<!-- Method Block -->
#### Methods


##### ccclass

Declare the standard [ES6 Class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
as CCClass, please see [Class](../../../manual/en/scripting/class.html) for details.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:246](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L246) |

###### Parameters
- `name` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> The class name used for serialization.

##### Examples

```js
const {ccclass} = cc._decorator;

// define a CCClass, omit the name
@ccclass
class NewScript extends cc.Component {
    // ...
}

// define a CCClass with a name
@ccclass('LoginData')
class LoginData {
    // ...
}
```

##### property

Declare property for [CCClass](../../../manual/en/scripting/reference/attributes.html).

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:318](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L318) |

###### Parameters
- `options` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> an object with some property attributes
	- `type` Any 
	- `visible` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> 
	- `displayName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
	- `tooltip` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
	- `multiline` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `readonly` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `min` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
	- `max` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
	- `step` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
	- `range` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number[]</a> 
	- `slide` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `serializable` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `editorOnly` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `override` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `animatable` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
	- `formerlySerializedAs` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
const {ccclass, property} = cc._decorator;

@ccclass
class NewScript extends cc.Component {
    @property({
        type: cc.Node
    })
    targetNode1 = null;

    @property(cc.Node)
    targetNode2 = null;

    @property(cc.Button)
    targetButton = null;

    @property
    _width = 100;

    @property
    get width () {
        return this._width;
    }

    @property
    set width (value) {
        this._width = value;
    }

    @property
    offset = new cc.Vec2(100, 100);

    @property(cc.Vec2)
    offsets = [];

    @property(cc.SpriteFrame)
    frame = null;
}

// above is equivalent to (上面的代码相当于):

var NewScript = cc.Class({
    properties: {
        targetNode1: {
            default: null,
            type: cc.Node
        },

        targetNode2: {
            default: null,
            type: cc.Node
        },

        targetButton: {
            default: null,
            type: cc.Button
        },

        _width: 100,

        width: {
            get () {
                return this._width;
            },
            set (value) {
                this._width = value;
            }
        },

        offset: new cc.Vec2(100, 100)

        offsets: {
            default: [],
            type: cc.Vec2
        }

        frame: {
            default: null,
            type: cc.SpriteFrame
        },
    }
});
```

##### executeInEditMode

Makes a CCClass that inherit from component execute in edit mode.<br>
By default, all components are only executed in play mode,
which means they will not have their callback functions executed while the Editor is in edit mode.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:464](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L464) |


##### Examples

```js
const {ccclass, executeInEditMode} = cc._decorator;

@ccclass
@executeInEditMode
class NewScript extends cc.Component {
    // ...
}
```

##### requireComponent

Automatically add required component as a dependency for the CCClass that inherit from component.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:488](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L488) |

###### Parameters
- `requiredComponent` <a href="../classes/Component.html" class="crosslink">Component</a> 

##### Examples

```js
const {ccclass, requireComponent} = cc._decorator;

@ccclass
@requireComponent(cc.Sprite)
class SpriteCtrl extends cc.Component {
    // ...
}
```

##### menu

The menu path to register a component to the editors "Component" menu. Eg. "Rendering/CameraCtrl".

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:509](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L509) |

###### Parameters
- `path` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> The path is the menu represented like a pathname.
                       For example the menu could be "Rendering/CameraCtrl".

##### Examples

```js
const {ccclass, menu} = cc._decorator;

@ccclass
@menu("Rendering/CameraCtrl")
class NewScript extends cc.Component {
    // ...
}
```

##### executionOrder

The execution order of lifecycle methods for Component.
Those less than 0 will execute before while those greater than 0 will execute after.
The order will only affect onLoad, onEnable, start, update and lateUpdate while onDisable and onDestroy will not be affected.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:531](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L531) |

###### Parameters
- `order` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The execution order of lifecycle methods for Component. Those less than 0 will execute before while those greater than 0 will execute after.

##### Examples

```js
const {ccclass, executionOrder} = cc._decorator;

@ccclass
@executionOrder(1)
class CameraCtrl extends cc.Component {
    // ...
}
```

##### disallowMultiple

Prevents Component of the same type (or subtype) to be added more than once to a Node.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:554](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L554) |


##### Examples

```js
const {ccclass, disallowMultiple} = cc._decorator;

@ccclass
@disallowMultiple
class CameraCtrl extends cc.Component {
    // ...
}
```

##### playOnFocus

If specified, the editor's scene view will keep updating this node in 60 fps when it is selected, otherwise, it will update only if necessary.<br>
This property is only available if executeInEditMode is true.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:575](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L575) |


##### Examples

```js
const {ccclass, playOnFocus, executeInEditMode} = cc._decorator;

@ccclass
@executeInEditMode
@playOnFocus
class CameraCtrl extends cc.Component {
    // ...
}
```

##### inspector

Specifying the url of the custom html to draw the component in **Properties**.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:598](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L598) |

###### Parameters
- `url` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
const {ccclass, inspector} = cc._decorator;

@ccclass
@inspector("packages://inspector/inspectors/comps/camera-ctrl.js")
class NewScript extends cc.Component {
    // ...
}
```

##### icon

Specifying the url of the icon to display in the editor.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:619](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L619) |

###### Parameters
- `url` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
const {ccclass, icon} = cc._decorator;

@ccclass
@icon("xxxx.png")
class NewScript extends cc.Component {
    // ...
}
```

##### help

The custom documentation URL.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:641](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L641) |

###### Parameters
- `url` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
const {ccclass, help} = cc._decorator;

@ccclass
@help("app://docs/html/components/spine.html")
class NewScript extends cc.Component {
    // ...
}
```

##### mixins

NOTE:<br>
The old mixins implemented in cc.Class(ES5) behaves exact the same as multiple inheritance.
But since ES6, class constructor can't be function-called and class methods become non-enumerable,
so we can not mix in ES6 Classes.<br>
See:<br>
[https://esdiscuss.org/topic/traits-are-now-impossible-in-es6-until-es7-since-rev32](https://esdiscuss.org/topic/traits-are-now-impossible-in-es6-until-es7-since-rev32)<br>
One possible solution (but IDE unfriendly):<br>
[http://justinfagnani.com/2015/12/21/real-mixins-with-javascript-classes](http://justinfagnani.com/2015/12/21/real-mixins-with-javascript-classes/)<br>
<br>
NOTE:<br>
You must manually call mixins constructor, this is different from cc.Class(ES5).

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCClassDecorator.js:664](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCClassDecorator.js#L664) |

###### Parameters
- `ctor` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> constructors to mix, only support ES5 constructors or classes defined by using `cc.Class`,
                            not support ES6 Classes.

##### Examples

```js
const {ccclass, mixins} = cc._decorator;

class Animal { ... }

const Fly = cc.Class({
    constructor () { ... }
});

@ccclass
@mixins(cc.EventTarget, Fly)
class Bird extends Animal {
    constructor () {
        super();

        // You must manually call mixins constructor, this is different from cc.Class(ES5)
        cc.EventTarget.call(this);
        Fly.call(this);
    }
    // ...
}
```


