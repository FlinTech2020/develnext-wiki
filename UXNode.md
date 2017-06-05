# UXNode

- **class** `UXnode` (`php\gui\UXNode`)
- **package** `gui`

> ������ ����������:

> [`UXParent`](UXParent), [`UXCanvas`](UXCanvas), [`UXImageView`](UXImageView)

������� ����� ��� ���� ���������� ����������� � DevelNext. �� ����� ������ ����������� ������, ������, ������ � ��� ���������. ��� ��������, ��� ��� ���������� ���������� ����� ������ � �������� ��������� ����!

#### ��������
- ���������
    - [id](#id-string), [parent](#parent-uxparent), [scene](#scene-uxscene), [form](#form-uxform),  [window](#window-uxwindow), [userData](#userdata-mixed)
- ������� ���
  - [style](#style-string), [effects](#effects-uxeffectpipeline), [clip](#clip-uxnode), [classes](#classes-uxlist), [classesString](#classesstring-string), [visible](#visible-bool), [enabled](#enabled-bool), [opacity](#opacity-double), [rotate](#rotate-double), [cursor](#cursor-string--uximage)
- ������� � �������
  - [x](#x-double), [y](#y-double), [position](#position-array), [screenX](#screenx-double), [screenY](#screeny-double), [translateX](#translatex-double), [translateY](#translatey-double), [translateZ](#translatez-double), [width](#width-double), [height](#height-double), [size](#size-array), [scaleX](#scalex-double), [scaleY](#scaleY-double), [layoutBounds](#layoutbounds-array), [boundsInParent](#boundsinparent-array), [managed](#managed-bool)
- ������
  - [mouseTransparent](#mousetransparent-bool), [focused](#focused-bool), [focusTraversable](#focustraversable-bool)

#### ������
- [�����������](#__construct) `__construct`
- ���������
  - [data()](#data), [free()](#free), [isFree()](#isfree), [lookup()](#lookup), [lookupAll()](#lookupall)
- ������� ���
  - [relocate()](#relocate), [resize()](#resize), [hide()](#hide), [show()](#show), [toggle()](#toggle), [toFront()](#tofront), [toBack()](#toback), [requestFocus()](#requestfocus), [snapshot()](#snapshot), [screenToLocal()](#screentolocal)
- �������
  - [on()](#on), [off()](#off), [trigger()](#trigger), [observer()](#observer)
- ������
  - [startFullDrag()](#startfulldrag), [startDrag()](#startdrag)


---

������ � ��������� ���������� ����������� ��������� �������:

```php
$var = $button->id; // id - ��� �������� ���������� �� ������ UXNode.
// ���
$var = $this->button->id;

// ��� ��������� �������� ���������� ����������:
$this->button->id = 'new_value';
```

---

## ��������

### `id` (string)
�������������.

---

### `style` (string)
CSS ����� ���������� � ���� ������.

---

### `parent` ([UXParent](UXParent))
������������ ���������.

---

### `effects` ([UXEffectPipeline](UXEffectPipeline))
������� ����������.

---

### `clip` ([UXNode](UXNode))
���������, �� ��������� �������� ���������� ������� ���������, ��-��������� `null`.

---

### `scene` ([UXScene](UXScene))
�����, �� ������� ��������� ���������.

---

### `form` ([UXForm](UXForm))
�����, �� ������� ��������� ���������.

---

### `window` ([UXWindow](UXWindow))
����, �� ������� ��������� ���������.

---

### `x` (double)
������� �� ��� X (��������������).

---

### `y` (double)
������� �� ��� Y (������������).

---

### `position` (array)
������ [x, y], ������� �� x � y.

```php
$button->position = [10, 30]; // 10 - x, 30 - y

list($x, $y) = $button->position;
```

---

### `translateX` (double)
�������� �� X �� ���������� ��������.

---

### `translateY` (double)
�������� �� Y �� ���������� ��������.

---

### `translateZ` (double)
�������� �� Z �� ���������� ��������.

---

### `scaleX` (double)
��������������� �� X, � ��������� �� 0 �� 1 � ����.

```php
$button->scaleX = 2.0; // ��������� ������ � 2 ����, 200% - �� ���������� �������.
```

---

### `scaleY` (double)
��������������� �� Y, � ��������� �� 0 �� 1 � ����.

---

### `screenX` (double)
���������� ������� ���������� �� X (�����������) �� ������.

---

### `screenY` (double)
���������� ������� ���������� �� Y (���������) �� ������.

---

### `width` (double)
������ ����������.

---

### `height` (double)
������ ����������.

---

### `size` (array)
������� ���������� [width, height] � ���� �������.

```php
$button->size = [100, 30]; // ������ 100, ������ 30

list($width, $height) = $button->size;
```

---

### `visible` (bool)
��������� ����������, ��-��������� `true`.

---

### `managed` (bool)
��������� �� ������� ���������� ��� ������� � ��������� �������� (layout), ��-��������� `true`.

---

### `enabled` (bool)
����������� ����������, ��-��������� `true`.

---

### `opacity` (bool)
���������������� ����������, �� 0 �� 1, ��� 0 - ������ �����������, 1 - ������ ��������������. ��-��������� `1.0`.

```php
$button->opacity = 0.7; // 70% �� ��������� �������.
```

---

### `rotate` (double)
���� ������� ����������, �� 0 �� 360 ��������, ��-��������� `0`.

---

### `focused` (bool)
> **������ ��� ������**

����� �� �� ���������� �����, �� - `true`, ��� - `false`.

---

### `focusTraversable` (bool)
����������� ����������� ����� ������� `tab`, ��-��������� `true`.

---

### `classes` ([UXList](UXList))
������ css ������� ��� ���������� JavaFX ������.

```php
$button->classes->add('my-button');
```

---

### `classesString` (string)
������ css ������� � ���� ����� ������, � �� UXList, ��� ��� ������ �������� ����� ����� ��������.

```
$button->classesString = 'my-button other-class';
```

---

### `userData` (mixed)
����� ���������������� ������, ������� ���������� ������� ������ ����������. ��. ����� ����� `data()`.

```php
$button->userData = 'my data string';
$button->userData = ['abcd', 'xyz', 3478];
```

> �������� ����� ������� ����� �������� - ������, �����, �������, ������� � �.�.

---

### `mouseTransparent` (bool)
������������� �������� �������, ��-��������� `false`. ���� ����� ���������, ��������� ���������� ����������� �� ����� ����� ������, ���� ��������� ������� � ����������� �� ������ �������.

---

### `cursor` (string / [UXImage](UXImage))
������ ��� ��������� �� ���������, ��-��������� `DEFAULT`. ���� ������ (���������� ��� �������), ���� ����������� (UXImage) - ����������� �������.

---

### `layoutBounds` (array)
> **������ ��� ������**

������� � ������� ���������� ������ ��� ������� (layout), ������ ����:

```php
['x' => 0.0, 'y' => 0.0, 'z' => 0.0, 'width' => 0.0, 'height' => 0.0, 'depth' => 0.0]
```

---

### `boundsInParent` (array)
> **������ ��� ������**

������� � ������� ���������� ������������ ��� ������������� ����������, ������ ����:

```php
['x' => 0.0, 'y' => 0.0, 'z' => 0.0, 'width' => 0.0, 'height' => 0.0, 'depth' => 0.0]
```

---

## ������

### `__construct()`
����������� ����������, �� ����� ����������, ���������.

---

### `data()`
```php
data(string $name[, mixed $value]): mixed
```
����� ��� �������� � ��������� ���������������� ������ �� ����������. ��������� ������� ����� ������, ��������� � �����������. 

> ��� ������������� ������ `data()`, �������� `userData` ����� ������������ � �������.

```php
// ������ ������
$button->data('key', 'my value');

// ��������� ������
$value = $button->data('key');
```

---

### `screenToLocal()`
```php
screenToLocal(double $x, double $y): array
```
��������� ���������� (x, y) �� ���������� (��������) � ���������. ���������� ������ ��������� `[x, y]`.

---

### snapshot()
```php
snapshot(): UXImage
```
������ �������� ���������� � ���������� ��� � ���� �������� ������� [UXImage](UXImage).

---

### lookup()
```php
lookup(string $selector): UXNode
```
���� ������ ��������� ����� ����������� �� css ��������� � ���������� ���. ���� ������ �� �������, ���������� `null`.

---

### `lookupAll`
```php
lookupAll($selector): UXNode[]
```
���� ��� ���������� ����� ����������� �� css ��������� � ���������� ��. ���� ������ �� �������, ���������� ������ ������.

---

### `resize()`
```php
resize(double $width, double $height)
```
������ ������ � ������� ����������. ��. ����� �������� [`size`](#size-array).

---

### `relocate()`
```php
relocate(double $x, double $y)
```
������ ������� (x, y) ����������. ��. ����� �������� [`position`](#position-array).

---

### `toFront()`
����������� ��������� ������ ���� ��������.

---

### `toBack()`
����������� ��������� ��� ��� �������.

---

### `requestFocus()`
��������� ����� �� ������.

---

### `hide()`
������ ������, ��. ����� �������� [`visible`](#visible-bool).

---

### `show()`
�������� ������, ��. ����� �������� [`visible`](#visible-bool).

---

### `toggle()`
�������� ������ ���� �� ����� � ������ ������ ���� �� ������������, ��. ����� �������� [`visible`](#visible-bool).

---

### `isFree()`
```php 
isFree(): bool
```
���������� true, ���� ������ �� ��������� �� �� ����� ������ �������.

---

### `free()`
���������� ������, ������� ��� � ������������� ����������.

---

### `startFullDrag()`
������ ������ ��������� drag-n-drop ��� ����������.

---

### `startDrag()`
```php
startDrag(array $modes): UXDragboard
```
������ ��������� drag-n-drop ��� ���������� � ��������� ������� ������ `$modes`. `$modes` ��� ������ �����, ������ ����� ���� ��������� �����:

- `MOVE` - �����������
- `COPY` - �����������
- `LINK` - ����������

����� ���������� ������ [UXDragboard](UXDragboard).

---

### `on()`
```php
on(string $event, callable $handler, $group = 'general')
```
����� ��������� �������-��������� `$handler` �� ������������ ������� `$event` ����������. ����� ����� ������� `$group` - ���������� ��� �������-���������, ��� ������ ����� ����� ����� ������������� ������ ���� �������-���������, ������� ��������� ����� `on()` � ���������� ��������� `$group` ����������� ��������� �������.

```php
$button->on('click', function ($e) {
    alert('������ ���');
});
```

---

### `off()`
```php
off(string $event[, string $group])
```
��������� �������-��������� �� ������� ����������. ���� �������� `$group`, �� ����� ��������� ���� ���� �������-��������� ��� ���� ���������� �����.

---

### `trigger()`
```php
trigger($event[, UXEvent $e])
```
������� �� ���������� ��� �������-��������� ������������� ������� ����������.

---

### `observer()`
```php
observer(string $property): UXValue
```
��������� ��������� �� ��������� ������������� �������� ����������. �� �� ��� �������� ���������� ����� �������� ���������.

```php
// ��� ��������� ��������� ����������.
$button->observer('visible')->addListener(function($oldValue, $newValue) {
    alert("������ �������� = $oldValue \n����� �������� = $newValue");
});
```