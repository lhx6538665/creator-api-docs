## `RigidBody` Class

Extends [`Component`](Component.md)


Module: [cc](../modules/cc.md)
Parent Module: [cc](../modules/cc.md)






### Index

##### Properties

  - [`enabledContactListener`](#enabledcontactlistener) `Boolean` Should enabled contact listener?...
  - [`bullet`](#bullet) `Boolean` - All bodies are prevented from tunneling through kinematic and static bodies.
  - [`type`](#type) `RigidBodyType` Rigidbody type : Static, Kinematic, Dynamic or Animated.
  - [`allowSleep`](#allowsleep) `Boolean` Set this flag to false if this body should never fall asleep.
  - [`gravityScale`](#gravityscale) `Number` Scale the gravity applied to this body.
  - [`linearDamping`](#lineardamping) `Number` Linear damping is use to reduce the linear velocity.
  - [`angularDamping`](#angulardamping) `Number` Angular damping is use to reduce the angular velocity.
  - [`linearVelocity`](#linearvelocity) `Vec2` The linear velocity of the body's origin in world co-ordinates.
  - [`angularVelocity`](#angularvelocity) `Number` The angular velocity of the body.
  - [`fixedRotation`](#fixedrotation) `Boolean` Should this body be prevented from rotating?
  - [`awake`](#awake) `Boolean` Set the sleep state of the body.
  - [`awakeOnLoad`](#awakeonload) `Boolean` Whether to wake up this rigid body during initialization
  - [`active`](#active) `Boolean` Set the active state of the body.
  - [`__eventTargets`](#eventtargets) `Array` Register all related EventTargets,...
  - [`node`](#node) `Node` The node this component is attached to.
  - [`uuid`](#uuid) `String` The uuid for editor.
  - [`_enabled`](#enabled) `Boolean` 
  - [`enabled`](#enabled) `Boolean` indicates whether this component is enabled or not.
  - [`enabledInHierarchy`](#enabledinhierarchy) `Boolean` indicates whether this component is enabled and its node is also active in the hierarchy.
  - [`_isOnLoadCalled`](#isonloadcalled) `Number` Returns a value which used to indicate the onLoad get called or not.
  - [`_name`](#name) `String` 
  - [`_objFlags`](#objflags) `Number` 
  - [`name`](#name) `String` The name of the object.
  - [`isValid`](#isvalid) `Boolean` Indicates whether the object is not yet destroyed.



##### Methods

  - [`onBeginContact`](#onbegincontact) Collision callback.
  - [`onEndContact`](#onendcontact) Collision callback.
  - [`onPreSolve`](#onpresolve) Collision callback.
  - [`onPostSolve`](#onpostsolve) Collision callback.
  - [`getLocalPoint`](#getlocalpoint) Gets a local point relative to the body's origin given a world point.
  - [`getWorldPoint`](#getworldpoint) Get the world coordinates of a point given the local coordinates.
  - [`getWorldVector`](#getworldvector) Get the world coordinates of a vector given the local coordinates.
  - [`getLocalVector`](#getlocalvector) Gets a local vector relative to the body's origin given a world vector.
  - [`getWorldPosition`](#getworldposition) Get the world body origin position.
  - [`getWorldRotation`](#getworldrotation) Get the world body rotation angle.
  - [`getLocalCenter`](#getlocalcenter) Get the local position of the center of mass.
  - [`getWorldCenter`](#getworldcenter) Get the world position of the center of mass.
  - [`getLinearVelocityFromWorldPoint`](#getlinearvelocityfromworldpoint) Get the world linear velocity of a world point attached to this body.
  - [`getMass`](#getmass) Get total mass of the body.
  - [`getInertia`](#getinertia) Get the rotational inertia of the body about the local origin.
  - [`getJointList`](#getjointlist) Get all the joints connect to the rigidbody.
  - [`applyForce`](#applyforce) Apply a force at a world point.
  - [`applyForceToCenter`](#applyforcetocenter) Apply a force to the center of mass.
  - [`applyTorque`](#applytorque) Apply a torque.
  - [`applyLinearImpulse`](#applylinearimpulse) Apply a impulse at a world point, This immediately modifies the velocity.
  - [`applyAngularImpulse`](#applyangularimpulse) Apply an angular impulse.
  - [`syncPosition`](#syncposition) Synchronize node's world position to box2d rigidbody's position.
  - [`syncRotation`](#syncrotation) Synchronize node's world angle to box2d rigidbody's angle.
  - [`update`](#update) This is a lifecycle method.
  - [`lateUpdate`](#lateupdate) This is a lifecycle method.
  - [`__preload`](#preload) `__preload` is called before every onLoad.
  - [`onLoad`](#onload) When attaching to an active node or its node first activated.
  - [`start`](#start) Called before all scripts' update if the Component is enabled the first time.
  - [`onEnable`](#onenable) This is a lifecycle method.
  - [`onDisable`](#ondisable) This is a lifecycle method.
  - [`onDestroy`](#ondestroy) This is a lifecycle method.
  - [`onFocusInEditor`](#onfocusineditor) 
  - [`onLostFocusInEditor`](#onlostfocusineditor) 
  - [`resetInEditor`](#resetineditor) Called to initialize the component or node’s properties when adding the component the first time or when the Reset command is used.
  - [`addComponent`](#addcomponent) Adds a component class to the node.
  - [`getComponent`](#getcomponent) Returns the component of supplied type if the node has one attached, null if it doesn't....
  - [`getComponents`](#getcomponents) Returns all components of supplied Type in the node.
  - [`getComponentInChildren`](#getcomponentinchildren) Returns the component of supplied type in any of its children using depth first search.
  - [`getComponentsInChildren`](#getcomponentsinchildren) Returns the components of supplied type in self or any of its children using depth first search.
  - [`_getLocalBounds`](#getlocalbounds) If the component's bounding box is different from the node's, you can implement this method to supply
  - [`onRestore`](#onrestore) for undo/redo operation.
  - [`schedule`](#schedule) Schedules a custom selector....
  - [`scheduleOnce`](#scheduleonce) Schedules a callback function that runs only once, with a delay of 0 or larger.
  - [`unschedule`](#unschedule) Unschedules a custom callback function.
  - [`unscheduleAllCallbacks`](#unscheduleallcallbacks) unschedule all scheduled callback functions: custom callback functions, and the 'update' callback function....
  - [`destroy`](#destroy) Actual object destruction will delayed until before rendering.
  - [`_destruct`](#destruct) Clear all references in the instance.
  - [`_onPreDestroy`](#onpredestroy) Called before the object being destroyed.
  - [`_serialize`](#serialize) The customized serialization for this object.
  - [`_deserialize`](#deserialize) Init this object from the custom serialized data.



### Details


#### Properties


##### enabledContactListener

> Should enabled contact listener?
When a collision is trigger, the collision callback will only be called when enabled contact listener.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:77](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L77) |



##### bullet

> Is this a fast moving body that should be prevented from tunneling through
other moving bodies?
Note :
- All bodies are prevented from tunneling through kinematic and static bodies. This setting is only considered on dynamic bodies.
- You should use this flag sparingly since it increases processing time.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:151](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L151) |



##### type

> Rigidbody type : Static, Kinematic, Dynamic or Animated.

| meta | description |
|------|-------------|
| Type | <a href="../enums/RigidBodyType.html" class="crosslink">RigidBodyType</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:171](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L171) |



##### allowSleep

> Set this flag to false if this body should never fall asleep.
Note that this increases CPU usage.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:199](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L199) |



##### gravityScale

> Scale the gravity applied to this body.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:226](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L226) |



##### linearDamping

> Linear damping is use to reduce the linear velocity.
The damping parameter can be larger than 1, but the damping effect becomes sensitive to the
time step when the damping parameter is large.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:247](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L247) |



##### angularDamping

> Angular damping is use to reduce the angular velocity. The damping parameter
can be larger than 1 but the damping effect becomes sensitive to the
time step when the damping parameter is large.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:270](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L270) |



##### linearVelocity

> The linear velocity of the body's origin in world co-ordinates.

| meta | description |
|------|-------------|
| Type | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:293](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L293) |



##### angularVelocity

> The angular velocity of the body.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:324](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L324) |



##### fixedRotation

> Should this body be prevented from rotating?

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:348](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L348) |



##### awake

> Set the sleep state of the body. A sleeping body has very low CPU cost.(When the rigid body is hit, if the rigid body is in sleep state, it will be immediately awakened.)

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:369](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L369) |



##### awakeOnLoad

> Whether to wake up this rigid body during initialization

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:390](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L390) |



##### active

> Set the active state of the body. An inactive body is not
simulated and cannot be collided with or woken up.
If body is active, all fixtures will be added to the
broad-phase.
If body is inactive, all fixtures will be removed from
the broad-phase and all contacts will be destroyed.
Fixtures on an inactive body are implicitly inactive and will
not participate in collisions, ray-casts, or queries.
Joints connected to an inactive body are implicitly inactive.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/physics/CCRigidBody.js:404](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L404) |



##### __eventTargets

> Register all related EventTargets,
all event callbacks will be removed in _onPreDestroy

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Array" class="crosslink external" target="_blank">Array</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:61](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L61) |



##### node

> The node this component is attached to. A component is always attached to a node.

| meta | description |
|------|-------------|
| Type | <a href="../classes/Node.html" class="crosslink">Node</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:75](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L75) |

##### Examples

```js
cc.log(comp.node);
```


##### uuid

> The uuid for editor.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:106](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L106) |

##### Examples

```js
cc.log(comp.uuid);
```


##### _enabled

> 

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:147](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L147) |



##### enabled

> indicates whether this component is enabled or not.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:154](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L154) |

##### Examples

```js
comp.enabled = true;
cc.log(comp.enabled);
```


##### enabledInHierarchy

> indicates whether this component is enabled and its node is also active in the hierarchy.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:186](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L186) |

##### Examples

```js
cc.log(comp.enabledInHierarchy);
```


##### _isOnLoadCalled

> Returns a value which used to indicate the onLoad get called or not.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/components/CCComponent.js:202](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L202) |

##### Examples

```js
cc.log(this._isOnLoadCalled > 0);
```


##### _name

> 

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/platform/CCObject.js:76](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L76) |



##### _objFlags

> 

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| Defined in | [cocos2d/core/platform/CCObject.js:83](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L83) |



##### name

> The name of the object.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| Defined in | [cocos2d/core/platform/CCObject.js:240](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L240) |

##### Examples

```js
obj.name = "New Obj";
```


##### isValid

> Indicates whether the object is not yet destroyed. (It will not be available after being destroyed)<br>
When an object's `destroy` is called, it is actually destroyed after the end of this frame.
So `isValid` will return false from the next frame, while `isValid` in the current frame will still be true.
If you want to determine whether the current frame has called `destroy`, use `cc.isValid(obj, true)`,
but this is often caused by a particular logical requirements, which is not normally required.

| meta | description |
|------|-------------|
| Type | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| Defined in | [cocos2d/core/platform/CCObject.js:258](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L258) |

##### Examples

```js
var node = new cc.Node();
cc.log(node.isValid);    // true
node.destroy();
cc.log(node.isValid);    // true, still valid in this frame
// after a frame...
cc.log(node.isValid);    // false, destroyed in the end of last frame
```





<!-- Method Block -->
#### Methods


##### onBeginContact

Collision callback.
Called when two collider begin to touch.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:92](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L92) |

###### Parameters
- `contact` <a href="../classes/PhysicsContact.html" class="crosslink">PhysicsContact</a> contact information
- `selfCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to this rigidbody
- `otherCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to another rigidbody


##### onEndContact

Collision callback.
Called when two collider cease to touch.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:104](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L104) |

###### Parameters
- `contact` <a href="../classes/PhysicsContact.html" class="crosslink">PhysicsContact</a> contact information
- `selfCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to this rigidbody
- `otherCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to another rigidbody


##### onPreSolve

Collision callback.
This is called when a contact is updated.
This allows you to inspect a contact before it goes to the solver(e.g. disable contact).
Note: this is called only for awake bodies.
Note: this is called even when the number of contact points is zero.
Note: this is not called for sensors.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:116](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L116) |

###### Parameters
- `contact` <a href="../classes/PhysicsContact.html" class="crosslink">PhysicsContact</a> contact information
- `selfCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to this rigidbody
- `otherCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to another rigidbody


##### onPostSolve

Collision callback.
This is called after a contact is updated.
You can get the impulses from the contact in this callback.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:136](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L136) |

###### Parameters
- `contact` <a href="../classes/PhysicsContact.html" class="crosslink">PhysicsContact</a> contact information
- `selfCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to this rigidbody
- `otherCollider` <a href="../classes/PhysicsCollider.html" class="crosslink">PhysicsCollider</a> the collider belong to another rigidbody


##### getLocalPoint

Gets a local point relative to the body's origin given a world point.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:437](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L437) |

###### Parameters
- `worldPoint` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> a point in world coordinates.
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving point


##### getWorldPoint

Get the world coordinates of a point given the local coordinates.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:458](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L458) |

###### Parameters
- `localPoint` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> a point in local coordinates.
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving point


##### getWorldVector

Get the world coordinates of a vector given the local coordinates.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:479](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L479) |

###### Parameters
- `localVector` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> a vector in world coordinates.
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving vector


##### getLocalVector

Gets a local vector relative to the body's origin given a world vector.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:500](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L500) |

###### Parameters
- `worldVector` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> a vector in world coordinates.
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving vector


##### getWorldPosition

Get the world body origin position.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:521](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L521) |

###### Parameters
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving point


##### getWorldRotation

Get the world body rotation angle.

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:540](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L540) |



##### getLocalCenter

Get the local position of the center of mass.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:555](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L555) |



##### getWorldCenter

Get the world position of the center of mass.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:573](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L573) |



##### getLinearVelocityFromWorldPoint

Get the world linear velocity of a world point attached to this body.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:591](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L591) |

###### Parameters
- `worldPoint` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> a point in world coordinates.
- `out` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> optional, the receiving point


##### getMass

Get total mass of the body.

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:612](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L612) |



##### getInertia

Get the rotational inertia of the body about the local origin.

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:624](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L624) |



##### getJointList

Get all the joints connect to the rigidbody.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Joint.html" class="crosslink">[Joint]</a> 
| Defined in | [cocos2d/core/physics/CCRigidBody.js:636](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L636) |



##### applyForce

Apply a force at a world point. If the force is not
applied at the center of mass, it will generate a torque and
affect the angular velocity.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:671](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L671) |

###### Parameters
- `force` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> the world force vector.
- `point` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> the world position.
- `wake` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> also wake up the body.


##### applyForceToCenter

Apply a force to the center of mass.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:691](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L691) |

###### Parameters
- `force` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> the world force vector.
- `wake` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> also wake up the body.


##### applyTorque

Apply a torque. This affects the angular velocity.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:707](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L707) |

###### Parameters
- `torque` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> about the z-axis (out of the screen), usually in N-m.
- `wake` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> also wake up the body


##### applyLinearImpulse

Apply a impulse at a world point, This immediately modifies the velocity.
If the impulse is not applied at the center of mass, it will generate a torque and
affect the angular velocity.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:722](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L722) |

###### Parameters
- `impulse` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> the world impulse vector, usually in N-seconds or kg-m/s.
- `point` <a href="../classes/Vec2.html" class="crosslink">Vec2</a> the world position
- `wake` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> alse wake up the body


##### applyAngularImpulse

Apply an angular impulse.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:743](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L743) |

###### Parameters
- `impulse` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> the angular impulse in units of kg*m*m/s
- `wake` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> also wake up the body


##### syncPosition

Synchronize node's world position to box2d rigidbody's position.
If enableAnimated is true and rigidbody's type is Animated type,
will set linear velocity instead of directly set rigidbody's position.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:758](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L758) |

###### Parameters
- `enableAnimated` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### syncRotation

Synchronize node's world angle to box2d rigidbody's angle.
If enableAnimated is true and rigidbody's type is Animated type,
will set angular velocity instead of directly set rigidbody's angle.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/physics/CCRigidBody.js:800](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/physics/CCRigidBody.js#L800) |

###### Parameters
- `enableAnimated` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### update

Update is called every frame, if the Component is enabled.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:223](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L223) |

###### Parameters
- `dt` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> the delta time in seconds it took to complete the last frame


##### lateUpdate

LateUpdate is called every frame, if the Component is enabled.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:234](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L234) |



##### __preload

`__preload` is called before every onLoad.
It is used to initialize the builtin components internally,
to avoid checking whether onLoad is called before every public method calls.
This method should be removed if script priority is supported.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:244](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L244) |



##### onLoad

When attaching to an active node or its node first activated.
onLoad is always called before any start functions, this allows you to order initialization of scripts.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:255](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L255) |



##### start

Called before all scripts' update if the Component is enabled the first time.
Usually used to initialize some logic which need to be called after all components' `onload` methods called.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:268](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L268) |



##### onEnable

Called when this component becomes enabled and its node is active.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:281](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L281) |



##### onDisable

Called when this component becomes disabled or its node becomes inactive.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:291](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L291) |



##### onDestroy

Called when this component will be destroyed.<br/>
This is a lifecycle method. It may not be implemented in the super class. You can only call its super class method inside it. It should not be called manually elsewhere.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:301](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L301) |



##### onFocusInEditor



| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:311](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L311) |



##### onLostFocusInEditor



| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:316](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L316) |



##### resetInEditor

Called to initialize the component or node’s properties when adding the component the first time or when the Reset command is used. This function is only called in editor.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:321](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L321) |



##### addComponent

Adds a component class to the node. You can also add component to node by passing in the name of the script.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Component.html" class="crosslink">Component</a> 
| Defined in | [cocos2d/core/components/CCComponent.js:331](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L331) |

###### Parameters
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> the constructor or the class name of the component to add

##### Examples

```js
var sprite = node.addComponent(cc.Sprite);
var test = node.addComponent("Test");
```

##### getComponent

Returns the component of supplied type if the node has one attached, null if it doesn't.<br/>
You can also get component in the node by passing in the name of the script.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Component.html" class="crosslink">Component</a> 
| Defined in | [cocos2d/core/components/CCComponent.js:349](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L349) |

###### Parameters
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
// get sprite component.
var sprite = node.getComponent(cc.Sprite);
// get custom test calss.
var test = node.getComponent("Test");
```

##### getComponents

Returns all components of supplied Type in the node.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| Defined in | [cocos2d/core/components/CCComponent.js:373](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L373) |

###### Parameters
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
var sprites = node.getComponents(cc.Sprite);
var tests = node.getComponents("Test");
```

##### getComponentInChildren

Returns the component of supplied type in any of its children using depth first search.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Component.html" class="crosslink">Component</a> 
| Defined in | [cocos2d/core/components/CCComponent.js:391](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L391) |

###### Parameters
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
var sprite = node.getComponentInChildren(cc.Sprite);
var Test = node.getComponentInChildren("Test");
```

##### getComponentsInChildren

Returns the components of supplied type in self or any of its children using depth first search.

| meta | description |
|------|-------------|
| Returns | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| Defined in | [cocos2d/core/components/CCComponent.js:409](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L409) |

###### Parameters
- `typeOrClassName` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### Examples

```js
var sprites = node.getComponentsInChildren(cc.Sprite);
var tests = node.getComponentsInChildren("Test");
```

##### _getLocalBounds

If the component's bounding box is different from the node's, you can implement this method to supply
a custom axis aligned bounding box (AABB), so the editor's scene view can perform hit test properly.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:429](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L429) |

###### Parameters
- `out_rect` <a href="../classes/Rect.html" class="crosslink">Rect</a> the Rect to receive the bounding box


##### onRestore

onRestore is called after the user clicks the Reset item in the Inspector's context menu or performs
an undo operation on this component.<br/>
<br/>
If the component contains the "internal state", short for "temporary member variables which not included<br/>
in its CCClass properties", then you may need to implement this function.<br/>
<br/>
The editor will call the getset accessors of your component to record/restore the component's state<br/>
for undo/redo operation. However, in extreme cases, it may not works well. Then you should implement<br/>
this function to manually synchronize your component's "internal states" with its public properties.<br/>
Once you implement this function, all the getset accessors of your component will not be called when<br/>
the user performs an undo/redo operation. Which means that only the properties with default value<br/>
will be recorded or restored by editor.<br/>
<br/>
Similarly, the editor may failed to reset your component correctly in extreme cases. Then if you need<br/>
to support the reset menu, you should manually synchronize your component's "internal states" with its<br/>
properties in this function. Once you implement this function, all the getset accessors of your component<br/>
will not be called during reset operation. Which means that only the properties with default value<br/>
will be reset by editor.

This function is only called in editor mode.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:442](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L442) |



##### schedule

Schedules a custom selector.<br/>
If the selector is already scheduled, then the interval parameter will be updated without scheduling it again.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:536](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L536) |

###### Parameters
- `callback` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> The callback function
- `interval` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Tick interval in seconds. 0 means tick every frame.
- `repeat` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The selector will be executed (repeat + 1) times, you can use cc.macro.REPEAT_FOREVER for tick infinitely.
- `delay` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### Examples

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.schedule(timeCallback, 1);
```

##### scheduleOnce

Schedules a callback function that runs only once, with a delay of 0 or larger.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:573](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L573) |

###### Parameters
- `callback` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector
- `delay` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### Examples

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.scheduleOnce(timeCallback, 2);
```

##### unschedule

Unschedules a custom callback function.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:590](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L590) |

###### Parameters
- `callback_fn` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector

##### Examples

```js
this.unschedule(_callback);
```

##### unscheduleAllCallbacks

unschedule all scheduled callback functions: custom callback functions, and the 'update' callback function.<br/>
Actions are not affected by this method.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/components/CCComponent.js:606](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/components/CCComponent.js#L606) |


##### Examples

```js
this.unscheduleAllCallbacks();
```

##### destroy

Destroy this Object, and release all its own references to other objects.<br/>
Actual object destruction will delayed until before rendering.
From the next frame, this object is not usable any more.
You can use cc.isValid(obj) to check whether the object is destroyed before accessing it.

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| Defined in | [cocos2d/core/platform/CCObject.js:293](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L293) |


##### Examples

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
| Defined in | [cocos2d/core/platform/CCObject.js:427](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L427) |



##### _onPreDestroy

Called before the object being destroyed.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCObject.js:460](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L460) |



##### _serialize

The customized serialization for this object. (Editor Only)

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">object</a> 
| Defined in | [cocos2d/core/platform/CCObject.js:485](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L485) |

###### Parameters
- `exporting` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### _deserialize

Init this object from the custom serialized data.

| meta | description |
|------|-------------|
| Defined in | [cocos2d/core/platform/CCObject.js:495](https://github.com/cocos-creator/engine/blob/b4415d3f111db35eb92e588d63bcb560003ea469/cocos2d/core/platform/CCObject.js#L495) |

###### Parameters
- `data` <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> the serialized json data
- `ctx` _Deserializer 



