# UXScreen
- **class** `UXScreen` (`php\gui\UXScreen`)
- **package** `gui`

```php
use php\gui\UXScreen;
```

����� ��� ������ � ����������� ������ ������������. � ������ ��������� �����������, ������� UXScreen ����� �������� ������ ����� ��������� ������:

---

#### ��������
> ��� �������� ������ ��� ������!

- `->`[`dpi`](#dpi-double) - _DPI ������_
- `->`[`bounds`](#bounds-array) - _������� ������_
- `->`[`visualBounds`](#visualbounds-array) - _������� ������� ������� ������_

#### ��������� ������
- `UXScreen ::`[`getPrimary()`](#getprimary) - _������� �����_
- `UXScreen ::`[`getScreens()`](#getscreens) - _������ ���� �������_

---

## ��������

### `dpi` (double)
DPI �������� ������. [https://ru.wikipedia.org/wiki/Dots_per_inch](https://ru.wikipedia.org/wiki/Dots_per_inch)

---

### `bounds` (array)
������� ������ � ���� �������:
```php
['x' => 0, 'y' => 0, 'width' => 0, 'height' => 0]
```

---

### `visualBounds` (array)
���������� ��������� ������ � ���� �������:
```php
['x' => 0, 'y' => 0, 'width' => 0, 'height' => 0]
```

> ������ ����� ��������� ������ ������� ������� ������, �� ���������� ������� ������������ �������.

---

## ��������� ������

### `getPrimary()`
���������� �������� ����� ������������ � ���� ������� ������ `UXScreen`.

```php
$screen = UXScreen::getPrimary();

$x = $screen->bounds['x'];
$y = $screen->bounds['y'];
$width = $screen->bounds['width'];
$height = $screen->bounds['height'];
```

---

### `getScreens()`
���������� ������ ������� � ���� ������� �������� ������ `UXScreen`:

```php
$screens = UXScreen::getScreens();

foreach ($screens as $screen) {
   pre($screen);
}
```