## `Skeleton` 类型

继承于 [`RenderComponent`](RenderComponent.md)


模块: [sp](../modules/sp.md)


Spine 骨骼动画 <br/>
<br/>
(Skeleton 具有对骨骼数据的引用并且存储了骨骼实例的状态，
它由当前的骨骼动作，slot 颜色，和可见的 slot attachments 组成。<br/>
多个 Skeleton 可以使用相同的骨骼数据，其中包括所有的动画，皮肤和 attachments。



### 索引

##### 属性（properties）

  - [`paused`](#paused) `Boolean` 该骨骼动画是否暂停。
  - [`skeletonData`](#skeletondata) `SkeletonData` attachments，皮肤等等）和动画但不持有任何状态。
  - [`defaultSkin`](#defaultskin) `String` 默认的皮肤名称。
  - [`defaultAnimation`](#defaultanimation) `String` 默认的动画名称。
  - [`animation`](#animation) `String` 当前播放的动画名称。
  - [`_defaultSkinIndex`](#defaultskinindex) `Number` 
  - [`loop`](#loop) `Boolean` 是否循环播放当前骨骼动画。
  - [`premultipliedAlpha`](#premultipliedalpha) `Boolean` 是否启用贴图预乘。
  - [`timeScale`](#timescale) `Number` 当前骨骼中所有动画的时间缩放率。
  - [`debugSlots`](#debugslots) `Boolean` 是否显示 slot 的 debug 信息。
  - [`debugBones`](#debugbones) `Boolean` 是否显示 bone 的 debug 信息。
  - [`useTint`](#usetint) `Boolean` 是否启用染色效果。
  - [`enableBatch`](#enablebatch) `Boolean` 开启合批，如果渲染大量相同纹理，且结构简单的骨骼动画，开启合批可以降低drawcall，否则请不要开启，cpu消耗会上升。
  - [`sharedMaterials`](#sharedmaterials) `[Material]` 渲染组件使用的材质。
  - [`__eventTargets`](#eventtargets) `Array` Register all related EventTargets,...
  - [`node`](#node) `Node` 该组件被附加到的节点。
  - [`uuid`](#uuid) `String` 组件的 uuid，用于编辑器。
  - [`_enabled`](#enabled) `Boolean` 
  - [`enabled`](#enabled) `Boolean` 表示该组件自身是否启用。
  - [`enabledInHierarchy`](#enabledinhierarchy) `Boolean` 表示该组件是否被启用并且所在的节点也处于激活状态。
  - [`_isOnLoadCalled`](#isonloadcalled) `Number` 返回一个值用来判断 onLoad 是否被调用过，不等于 0 时调用过，等于 0 时未调用。
  - [`_name`](#name) `String` 
  - [`_objFlags`](#objflags) `Number` 
  - [`name`](#name) `String` 该对象的名称。
  - [`isValid`](#isvalid) `Boolean` 表示该对象是否可用（被 destroy 后将不可用）。



##### 方法

  - [`setSkeletonData`](#setskeletondata) 设置底层运行时用到的 SkeletonData。
  - [`setSlotsRange`](#setslotsrange) 设置骨骼插槽可视范围。
  - [`setAnimationStateData`](#setanimationstatedata) 设置动画状态数据。
  - [`setAnimationCacheMode`](#setanimationcachemode) 若想切换渲染模式，最好在设置'dragonAsset'之前，先设置好渲染模式，否则有运行时开销。
  - [`isAnimationCached`](#isanimationcached) 当前是否处于缓存模式。
  - [`updateWorldTransform`](#updateworldtransform) 当获取 bone 的数值未更新时，即可使用该函数进行更新数值。
  - [`setToSetupPose`](#settosetuppose) 还原到起始动作
  - [`setBonesToSetupPose`](#setbonestosetuppose) 使用 SkeletonData 中的 BoneData 列表中的值。
  - [`setSlotsToSetupPose`](#setslotstosetuppose) 设置 slot 到起始动作。
  - [`updateAnimationCache`](#updateanimationcache) 更新某个动画缓存。
  - [`findBone`](#findbone) 通过名称查找 bone。
  - [`findSlot`](#findslot) 通过名称查找 slot。
  - [`setSkin`](#setskin) 按名称查找皮肤，激活该皮肤。
  - [`getAttachment`](#getattachment) 通过 slot 和 attachment 的名称获取 attachment。
  - [`setAttachment`](#setattachment) 通过 slot 和 attachment 的名字来设置 attachment。
  - [`getTextureAtlas`](#gettextureatlas) Return the renderer of attachment.
  - [`setMix`](#setmix) 为所有关键帧设定混合及混合时间（从当前值开始差值）。
  - [`setAnimation`](#setanimation) 设置当前动画。
  - [`addAnimation`](#addanimation) 添加一个动画到动画队列尾部，还可以延迟指定的秒数。
  - [`findAnimation`](#findanimation) 查找指定名称的动画
  - [`getCurrent`](#getcurrent) 通过 track 索引获取 TrackEntry。
  - [`clearTracks`](#cleartracks) 清除所有 track 的动画状态。
  - [`clearTrack`](#cleartrack) 清除出指定 track 的动画状态。
  - [`setStartListener`](#setstartlistener) 用来设置开始播放动画的事件监听。
  - [`setInterruptListener`](#setinterruptlistener) 用来设置动画被打断的事件监听。
  - [`setEndListener`](#setendlistener) 用来设置动画播放完后的事件监听。
  - [`setDisposeListener`](#setdisposelistener) 用来设置动画将被销毁的事件监听。
  - [`setCompleteListener`](#setcompletelistener) 用来设置动画播放一次循环结束后的事件监听。
  - [`setEventListener`](#seteventlistener) 用来设置动画播放过程中帧事件的监听。
  - [`setTrackStartListener`](#settrackstartlistener) 用来为指定的 TrackEntry 设置动画开始播放的事件监听。
  - [`setTrackInterruptListener`](#settrackinterruptlistener) 用来为指定的 TrackEntry 设置动画被打断的事件监听。
  - [`setTrackEndListener`](#settrackendlistener) 用来为指定的 TrackEntry 设置动画播放结束的事件监听。
  - [`setTrackDisposeListener`](#settrackdisposelistener) 用来为指定的 TrackEntry 设置动画即将被销毁的事件监听。
  - [`setTrackCompleteListener`](#settrackcompletelistener) 用来为指定的 TrackEntry 设置动画一次循环播放结束的事件监听。
  - [`setTrackEventListener`](#settrackeventlistener) 用来为指定的 TrackEntry 设置动画帧事件的监听。
  - [`setTrackEventListener`](#settrackeventlistener) 获取
  - [`getMaterial`](#getmaterial) 根据指定索引获取材质
  - [`setMaterial`](#setmaterial) 根据指定索引设置材质
  - [`update`](#update) 如果该组件启用，则每帧调用 update。
  - [`lateUpdate`](#lateupdate) 如果该组件启用，则每帧调用 LateUpdate。
  - [`__preload`](#preload) `__preload` is called before every onLoad....
  - [`onLoad`](#onload) 当附加到一个激活的节点上或者其节点第一次激活时候调用。
  - [`start`](#start) 如果该组件第一次启用，则在所有组件的 update 之前调用。
  - [`onEnable`](#onenable) 当该组件被启用，并且它的节点也激活时。
  - [`onDisable`](#ondisable) 当该组件被禁用或节点变为无效时调用。
  - [`onDestroy`](#ondestroy) 该方法为生命周期方法，父类未必会有实现。
  - [`onFocusInEditor`](#onfocusineditor) 
  - [`onLostFocusInEditor`](#onlostfocusineditor) 
  - [`resetInEditor`](#resetineditor) 用来初始化组件或节点的一些属性，当该组件被第一次添加到节点上或用户点击了它的 Reset 菜单时调用。
  - [`addComponent`](#addcomponent) 向节点添加一个组件类，你还可以通过传入脚本的名称来添加组件。
  - [`getComponent`](#getcomponent) 获取节点上指定类型的组件，如果节点有附加指定类型的组件，则返回，如果没有则为空。
  - [`getComponents`](#getcomponents) 返回节点上指定类型的所有组件。
  - [`getComponentInChildren`](#getcomponentinchildren) 递归查找所有子节点中第一个匹配指定类型的组件。
  - [`getComponentsInChildren`](#getcomponentsinchildren) 递归查找自身或所有子节点中指定类型的组件
  - [`_getLocalBounds`](#getlocalbounds) 以便编辑器的场景视图可以正确地执行点选测试。
  - [`onRestore`](#onrestore) onRestore 是用户在检查器菜单点击 Reset 时，对此组件执行撤消操作后调用的。
  - [`schedule`](#schedule) 调度一个自定义的回调函数。
  - [`scheduleOnce`](#scheduleonce) 调度一个只运行一次的回调函数，可以指定 0 让回调函数在下一帧立即执行或者在一定的延时之后执行。
  - [`unschedule`](#unschedule) 取消调度一个自定义的回调函数。
  - [`unscheduleAllCallbacks`](#unscheduleallcallbacks) 取消调度所有已调度的回调函数：定制的回调函数以及 'update' 回调函数。
  - [`destroy`](#destroy) 销毁该对象，并释放所有它对其它对象的引用。
  - [`_destruct`](#destruct) Clear all references in the instance....
  - [`_onPreDestroy`](#onpredestroy) Called before the object being destroyed.
  - [`_serialize`](#serialize) The customized serialization for this object. (Editor Only)
  - [`_deserialize`](#deserialize) Init this object from the custom serialized data.



### Details


#### 属性（properties）


##### paused

> 该骨骼动画是否暂停。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:108](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L108) |



##### skeletonData

> 骨骼数据包含了骨骼信息（绑定骨骼动作，slots，渲染顺序，
attachments，皮肤等等）和动画但不持有任何状态。<br/>
多个 Skeleton 可以共用相同的骨骼数据。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/SkeletonData.html" class="crosslink">SkeletonData</a> |
| 定义于 | [extensions/spine/Skeleton.js:121](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L121) |



##### defaultSkin

> 默认的皮肤名称。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [extensions/spine/Skeleton.js:147](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L147) |



##### defaultAnimation

> 默认的动画名称。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [extensions/spine/Skeleton.js:157](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L157) |



##### animation

> 当前播放的动画名称。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [extensions/spine/Skeleton.js:167](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L167) |



##### _defaultSkinIndex

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [extensions/spine/Skeleton.js:194](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L194) |



##### loop

> 是否循环播放当前骨骼动画。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:295](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L295) |



##### premultipliedAlpha

> 是否启用贴图预乘。
当图片的透明区域出现色块时需要关闭该选项，当图片的半透明区域颜色变黑时需要启用该选项。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:306](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L306) |



##### timeScale

> 当前骨骼中所有动画的时间缩放率。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [extensions/spine/Skeleton.js:320](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L320) |



##### debugSlots

> 是否显示 slot 的 debug 信息。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:331](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L331) |



##### debugBones

> 是否显示 bone 的 debug 信息。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:346](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L346) |



##### useTint

> 是否启用染色效果。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:361](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L361) |



##### enableBatch

> 开启合批，如果渲染大量相同纹理，且结构简单的骨骼动画，开启合批可以降低drawcall，否则请不要开启，cpu消耗会上升。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [extensions/spine/Skeleton.js:375](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L375) |



##### sharedMaterials

> 渲染组件使用的材质。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Material.html" class="crosslink">[Material]</a> |
| 定义于 | [cocos2d/core/components/CCRenderComponent.js:61](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCRenderComponent.js#L61) |



##### __eventTargets

> Register all related EventTargets,
all event callbacks will be removed in _onPreDestroy

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Array" class="crosslink external" target="_blank">Array</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:61](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L61) |



##### node

> 该组件被附加到的节点。组件总会附加到一个节点。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Node.html" class="crosslink">Node</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:75](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L75) |

##### 示例

```js
cc.log(comp.node);
```


##### uuid

> 组件的 uuid，用于编辑器。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:106](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L106) |

##### 示例

```js
cc.log(comp.uuid);
```


##### _enabled

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:147](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L147) |



##### enabled

> 表示该组件自身是否启用。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:154](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L154) |

##### 示例

```js
comp.enabled = true;
cc.log(comp.enabled);
```


##### enabledInHierarchy

> 表示该组件是否被启用并且所在的节点也处于激活状态。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:186](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L186) |

##### 示例

```js
cc.log(comp.enabledInHierarchy);
```


##### _isOnLoadCalled

> 返回一个值用来判断 onLoad 是否被调用过，不等于 0 时调用过，等于 0 时未调用。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [cocos2d/core/components/CCComponent.js:202](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L202) |

##### 示例

```js
cc.log(this._isOnLoadCalled > 0);
```


##### _name

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [cocos2d/core/platform/CCObject.js:76](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L76) |



##### _objFlags

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [cocos2d/core/platform/CCObject.js:83](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L83) |



##### name

> 该对象的名称。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [cocos2d/core/platform/CCObject.js:240](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L240) |

##### 示例

```js
obj.name = "New Obj";
```


##### isValid

> 表示该对象是否可用（被 destroy 后将不可用）。<br>
当一个对象的 `destroy` 调用以后，会在这一帧结束后才真正销毁。因此从下一帧开始 `isValid` 就会返回 false，而当前帧内 `isValid` 仍然会是 true。如果希望判断当前帧是否调用过 `destroy`，请使用 `cc.isValid(obj, true)`，不过这往往是特殊的业务需求引起的，通常情况下不需要这样。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [cocos2d/core/platform/CCObject.js:258](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L258) |

##### 示例

```js
var node = new cc.Node();
cc.log(node.isValid);    // true
node.destroy();
cc.log(node.isValid);    // true, still valid in this frame
// after a frame...
cc.log(node.isValid);    // false, destroyed in the end of last frame
```





<!-- Method Block -->
#### 方法


##### setSkeletonData

设置底层运行时用到的 SkeletonData。<br>
这个接口有别于 `skeletonData` 属性，这个接口传入的是 Spine runtime 提供的原始数据，而 skeletonData 的类型是 Creator 提供的资源类型。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:452](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L452) |

###### 参数列表
- `skeletonData` sp.spine.SkeletonData 


##### setSlotsRange

设置骨骼插槽可视范围。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:490](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L490) |

###### 参数列表
- `skeletonData` sp.spine.SkeletonData 


##### setAnimationStateData

设置动画状态数据。<br>
参数是 <a href="../modules/sp.spine.html">sp.spine</a>.AnimationStateData。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:505](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L505) |

###### 参数列表
- `stateData` sp.spine.AnimationStateData 


##### setAnimationCacheMode

若想切换渲染模式，最好在设置'dragonAsset'之前，先设置好渲染模式，否则有运行时开销。
若在编辑中设置渲染模式，则无需担心设置次序的问题。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:558](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L558) |

###### 参数列表
- `cacheMode` AnimationCacheMode 

##### 示例

```js
skeleton.setAnimationCacheMode(sp.Skeleton.AnimationCacheMode.SHARED_CACHE);
```

##### isAnimationCached

当前是否处于缓存模式。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:579](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L579) |



##### updateWorldTransform

重新更新所有骨骼的世界 Transform，
当获取 bone 的数值未更新时，即可使用该函数进行更新数值。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:697](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L697) |


##### 示例

```js
var bone = spine.findBone('head');
cc.log(bone.worldX); // return 0;
spine.updateWorldTransform();
bone = spine.findBone('head');
cc.log(bone.worldX); // return -23.12;
```

##### setToSetupPose

还原到起始动作

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:717](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L717) |



##### setBonesToSetupPose

设置 bone 到起始动作
使用 SkeletonData 中的 BoneData 列表中的值。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:732](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L732) |



##### setSlotsToSetupPose

设置 slot 到起始动作。
使用 SkeletonData 中的 SlotData 列表中的值。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:751](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L751) |



##### updateAnimationCache

更新某个动画缓存。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:770](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L770) |

###### 参数列表
- `animName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### findBone

通过名称查找 bone。
这里对每个 bone 的名称进行了对比。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.Bone 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.Bone 
| 定义于 | [extensions/spine/Skeleton.js:784](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L784) |

###### 参数列表
- `boneName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### findSlot

通过名称查找 slot。这里对每个 slot 的名称进行了比较。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.Slot 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.Slot 
| 定义于 | [extensions/spine/Skeleton.js:805](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L805) |

###### 参数列表
- `slotName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### setSkin

按名称查找皮肤，激活该皮肤。这里对每个皮肤的名称进行了比较。<br>
注意：设置皮肤不会改变 attachment 的可见性。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.Skin 对象。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:824](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L824) |

###### 参数列表
- `skinName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getAttachment

通过 slot 和 attachment 的名称获取 attachment。Skeleton 优先查找它的皮肤，然后才是 Skeleton Data 中默认的皮肤。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.Attachment 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.Attachment 
| 定义于 | [extensions/spine/Skeleton.js:849](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L849) |

###### 参数列表
- `slotName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `attachmentName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### setAttachment

通过 slot 和 attachment 的名字来设置 attachment。
Skeleton 优先查找它的皮肤，然后才是 Skeleton Data 中默认的皮肤。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:870](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L870) |

###### 参数列表
- `slotName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `attachmentName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getTextureAtlas

Return the renderer of attachment.

| meta | description |
|------|-------------|
| 返回 | sp.spine.TextureAtlasRegion 
| 定义于 | [extensions/spine/Skeleton.js:887](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L887) |

###### 参数列表
- `regionAttachment` sp.spine.RegionAttachment &#124; spine.BoundingBoxAttachment 


##### setMix

为所有关键帧设定混合及混合时间（从当前值开始差值）。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:898](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L898) |

###### 参数列表
- `fromAnimation` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `toAnimation` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `duration` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### setAnimation

设置当前动画。队列中的任何的动画将被清除。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.TrackEntry 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.TrackEntry 
| 定义于 | [extensions/spine/Skeleton.js:914](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L914) |

###### 参数列表
- `trackIndex` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- `name` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `loop` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### addAnimation

添加一个动画到动画队列尾部，还可以延迟指定的秒数。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.TrackEntry 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.TrackEntry 
| 定义于 | [extensions/spine/Skeleton.js:961](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L961) |

###### 参数列表
- `trackIndex` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- `name` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- `loop` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
- `delay` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### findAnimation

查找指定名称的动画

| meta | description |
|------|-------------|
| 返回 | sp.spine.Animation 
| 定义于 | [extensions/spine/Skeleton.js:993](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L993) |

###### 参数列表
- `name` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getCurrent

通过 track 索引获取 TrackEntry。<br>
返回一个 <a href="../modules/sp.spine.html">sp.spine</a>.TrackEntry 对象。

| meta | description |
|------|-------------|
| 返回 | sp.spine.TrackEntry 
| 定义于 | [extensions/spine/Skeleton.js:1007](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1007) |

###### 参数列表
- `trackIndex` Unknown 


##### clearTracks

清除所有 track 的动画状态。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1027](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1027) |



##### clearTrack

清除出指定 track 的动画状态。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1042](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1042) |

###### 参数列表
- `trackIndex` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">number</a> 


##### setStartListener

用来设置开始播放动画的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1061](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1061) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setInterruptListener

用来设置动画被打断的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1072](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1072) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setEndListener

用来设置动画播放完后的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1083](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1083) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setDisposeListener

用来设置动画将被销毁的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1094](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1094) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setCompleteListener

用来设置动画播放一次循环结束后的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1105](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1105) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setEventListener

用来设置动画播放过程中帧事件的监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1116](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1116) |

###### 参数列表
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackStartListener

用来为指定的 TrackEntry 设置动画开始播放的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1127](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1127) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackInterruptListener

用来为指定的 TrackEntry 设置动画被打断的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1138](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1138) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackEndListener

用来为指定的 TrackEntry 设置动画播放结束的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1149](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1149) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackDisposeListener

用来为指定的 TrackEntry 设置动画即将被销毁的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1160](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1160) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackCompleteListener

用来为指定的 TrackEntry 设置动画一次循环播放结束的事件监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1171](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1171) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 
	- `entry` sp.spine.TrackEntry 
	- `loopCount` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### setTrackEventListener

用来为指定的 TrackEntry 设置动画帧事件的监听。

| meta | description |
|------|-------------|
| 定义于 | [extensions/spine/Skeleton.js:1187](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1187) |

###### 参数列表
- `entry` sp.spine.TrackEntry 
- `listener` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> 


##### setTrackEventListener

获取

| meta | description |
|------|-------------|
| 返回 | sp.spine.AnimationState 
| 定义于 | [extensions/spine/Skeleton.js:1198](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/extensions/spine/Skeleton.js#L1198) |



##### getMaterial

根据指定索引获取材质

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCRenderComponent.js:167](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCRenderComponent.js#L167) |

###### 参数列表
- `index` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### setMaterial

根据指定索引设置材质

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCRenderComponent.js:189](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCRenderComponent.js#L189) |

###### 参数列表
- `index` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- `material` <a href="../classes/Material.html" class="crosslink">Material</a> 


##### update

如果该组件启用，则每帧调用 update。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:223](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L223) |

###### 参数列表
- `dt` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> the delta time in seconds it took to complete the last frame


##### lateUpdate

如果该组件启用，则每帧调用 LateUpdate。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:234](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L234) |



##### __preload

`__preload` is called before every onLoad.
It is used to initialize the builtin components internally,
to avoid checking whether onLoad is called before every public method calls.
This method should be removed if script priority is supported.

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:244](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L244) |



##### onLoad

当附加到一个激活的节点上或者其节点第一次激活时候调用。onLoad 总是会在任何 start 方法调用前执行，这能用于安排脚本的初始化顺序。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:255](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L255) |



##### start

如果该组件第一次启用，则在所有组件的 update 之前调用。通常用于需要在所有组件的 onLoad 初始化完毕后执行的逻辑。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:268](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L268) |



##### onEnable

当该组件被启用，并且它的节点也激活时。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:281](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L281) |



##### onDisable

当该组件被禁用或节点变为无效时调用。<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:291](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L291) |



##### onDestroy

当该组件被销毁时调用<br/>
该方法为生命周期方法，父类未必会有实现。并且你只能在该方法内部调用父类的实现，不可在其它地方直接调用该方法。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:301](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L301) |



##### onFocusInEditor



| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:311](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L311) |



##### onLostFocusInEditor



| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:316](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L316) |



##### resetInEditor

用来初始化组件或节点的一些属性，当该组件被第一次添加到节点上或用户点击了它的 Reset 菜单时调用。这个回调只会在编辑器下调用。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:321](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L321) |



##### addComponent

向节点添加一个组件类，你还可以通过传入脚本的名称来添加组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [cocos2d/core/components/CCComponent.js:331](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L331) |

###### 参数列表
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> the constructor or the class name of the component to add

##### 示例

```js
var sprite = node.addComponent(cc.Sprite);
var test = node.addComponent("Test");
```

##### getComponent

获取节点上指定类型的组件，如果节点有附加指定类型的组件，则返回，如果没有则为空。<br/>
传入参数也可以是脚本的名称。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [cocos2d/core/components/CCComponent.js:349](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L349) |

###### 参数列表
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
// get sprite component.
var sprite = node.getComponent(cc.Sprite);
// get custom test calss.
var test = node.getComponent("Test");
```

##### getComponents

返回节点上指定类型的所有组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| 定义于 | [cocos2d/core/components/CCComponent.js:373](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L373) |

###### 参数列表
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprites = node.getComponents(cc.Sprite);
var tests = node.getComponents("Test");
```

##### getComponentInChildren

递归查找所有子节点中第一个匹配指定类型的组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [cocos2d/core/components/CCComponent.js:391](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L391) |

###### 参数列表
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprite = node.getComponentInChildren(cc.Sprite);
var Test = node.getComponentInChildren("Test");
```

##### getComponentsInChildren

递归查找自身或所有子节点中指定类型的组件

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| 定义于 | [cocos2d/core/components/CCComponent.js:409](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L409) |

###### 参数列表
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprites = node.getComponentsInChildren(cc.Sprite);
var tests = node.getComponentsInChildren("Test");
```

##### _getLocalBounds

如果组件的包围盒与节点不同，您可以实现该方法以提供自定义的轴向对齐的包围盒（AABB），
以便编辑器的场景视图可以正确地执行点选测试。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:429](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L429) |

###### 参数列表
- `out_rect` <a href="../classes/Rect.html" class="crosslink">Rect</a> the Rect to receive the bounding box


##### onRestore

onRestore 是用户在检查器菜单点击 Reset 时，对此组件执行撤消操作后调用的。<br/>
<br/>
如果组件包含了“内部状态”（不在 CCClass 属性中定义的临时成员变量），那么你可能需要实现该方法。<br/>
<br/>
编辑器执行撤销/重做操作时，将调用组件的 get set 来录制和还原组件的状态。
然而，在极端的情况下，它可能无法良好运作。<br/>
那么你就应该实现这个方法，手动根据组件的属性同步“内部状态”。
一旦你实现这个方法，当用户撤销或重做时，组件的所有 get set 都不会再被调用。
这意味着仅仅指定了默认值的属性将被编辑器记录和还原。<br/>
<br/>
同样的，编辑可能无法在极端情况下正确地重置您的组件。<br/>
于是如果你需要支持组件重置菜单，你需要在该方法中手工同步组件属性到“内部状态”。<br/>
一旦你实现这个方法，组件的所有 get set 都不会在重置操作时被调用。
这意味着仅仅指定了默认值的属性将被编辑器重置。
<br/>
此方法仅在编辑器下会被调用。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:442](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L442) |



##### schedule

调度一个自定义的回调函数。<br/>
如果回调函数已调度，那么将不会重复调度它，只会更新时间间隔参数。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:536](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L536) |

###### 参数列表
- `callback` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> The callback function
- `interval` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Tick interval in seconds. 0 means tick every frame.
- `repeat` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The selector will be executed (repeat + 1) times, you can use cc.macro.REPEAT_FOREVER for tick infinitely.
- `delay` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### 示例

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.schedule(timeCallback, 1);
```

##### scheduleOnce

调度一个只运行一次的回调函数，可以指定 0 让回调函数在下一帧立即执行或者在一定的延时之后执行。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:573](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L573) |

###### 参数列表
- `callback` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector
- `delay` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### 示例

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.scheduleOnce(timeCallback, 2);
```

##### unschedule

取消调度一个自定义的回调函数。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:590](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L590) |

###### 参数列表
- `callback_fn` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector

##### 示例

```js
this.unschedule(_callback);
```

##### unscheduleAllCallbacks

取消调度所有已调度的回调函数：定制的回调函数以及 'update' 回调函数。动作不受此方法影响。

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/components/CCComponent.js:606](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L606) |


##### 示例

```js
this.unscheduleAllCallbacks();
```

##### destroy

销毁该对象，并释放所有它对其它对象的引用。<br/>
实际销毁操作会延迟到当前帧渲染前执行。从下一帧开始，该对象将不再可用。
您可以在访问对象之前使用 cc.isValid(obj) 来检查对象是否已被销毁。

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [cocos2d/core/platform/CCObject.js:293](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L293) |


##### 示例

```js
obj.destroy();
```

##### _destruct

Clear all references in the instance.

NOTE: this method will not clear the getter or setter functions which defined in the instance of CCObject.
      You can override the _destruct method if you need, for example:
      _destruct: function () {
          for (var key in this) {
              if (this.hasOwnProperty(key)) {
                  switch (typeof this[key]) {
                      case 'string':
                          this[key] = '';
                          break;
                      case 'object':
                      case 'function':
                          this[key] = null;
                          break;
              }
          }
      }

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/platform/CCObject.js:427](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L427) |



##### _onPreDestroy

Called before the object being destroyed.

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/platform/CCObject.js:460](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L460) |



##### _serialize

The customized serialization for this object. (Editor Only)

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">object</a> 
| 定义于 | [cocos2d/core/platform/CCObject.js:485](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L485) |

###### 参数列表
- `exporting` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### _deserialize

Init this object from the custom serialized data.

| meta | description |
|------|-------------|
| 定义于 | [cocos2d/core/platform/CCObject.js:495](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L495) |

###### 参数列表
- `data` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> the serialized json data
- `ctx` _Deserializer 



