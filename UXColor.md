# UXColor

- **class** `UXColor` (`php\gui\paint\UXColor`)
- **package** `gui`

```php
use php\gui\paint\UXColor;
```

����� ��������, ���������� �� ������������� ����� � ������ DevelNext. ������ ��� ���� � ���������� �����-������������ - ARGB:
- `alpha, red, gree, blue` (`�����, �������, �������, �����`).

> ������� ������� ������ ������������, ����� ������� ����� ����, ����� ������� ����� ������ ������ UXColor.

#### ��������
> ��� �������� ������ ��� ������!

- `->`[`red`](#red-double) - _������� ��������_
- `->`[`green`](#green-double) - _������� ��������_
- `->`[`blue`](#blue-double) - _������� ������_
- `->`[`opacity`](#opacity-double) - _������������_
- `->`[`brightness`](#brightness-double) - _�������_
- `->`[`hue`](#hue-double) - _�������_
- `->`[`saturation`](#saturation-double) - _������������_
- `->`[`webValue`](#webvalue-string) - _HTML ��� �����_

#### ������
- [�����������](#__construct) `__construct` - _�������� �����_
- `->`[`grayscale()`](#grayscale) - _�����-����� ������_
- `->`[`invert()`](#invert) - _�������������_
- `->`[`saturate()`](#saturate) - _����� ���������� ����_
- `->`[`desaturate()`](#desaturate) - _����� ���������� ����_
- `->`[`interpolate()`](#interpolate) - _������������ �����_
- `->`[`getRGB()`](#getrgb) - _RGB int �������� �����_
- `->`[`getWebValue()`](#getwebvalue) - _HTML ��� �����_

#### ��������� ������
- `UXColor:: `[`of()`](#of) - _�������� �����_
- `UXColor:: `[`rgb()`](#rgb) - _�������� ����� �� r, g, b_

---

## ��������

### `red` (double)
������� �������� �� 0 �� 1, ��� 1 = 100%.

---

### `green` (double)
������� �������� �� 0 �� 1, ��� 1 = 100%.

---

### `blue` (double)
������� ������ �� 0 �� 1, ��� 1 = 100%.

---

### `opacity` (double)
������� �����-������������ ����� �� 0 �� 1, ��� 1 = 100% ��������������. 

---

### `brightness` (double)
������� ������� ����� �� 0 �� 1.

---

### `hue` (double)
������� ������� (HUE) �� 0 �� 1.

---

### `saturation` (double)
������� ��������� ����� �� 0 �� 1.

---

### `webValue` (string)
������������� ����� � ���� HTML �����, ������ ������������ � `#`, �������� `#637DFAC`.

---

## ������

### `__construct()`
```php
__construct(double $r, double $g, double $b, double $opacity = 1.0)
```

```php
$r = 0.5;
$g = 0.6;
$b = 0.7;
$color = new UXColor($r, $g, $b, 0.8);
```

---

### `grayscale()`
```php
grayscale(): UXColor
```
���������� �����-����� ������ �����.

---

### `invert()`
```php
invert(): UXColor
```
���������� ��������������� ������ �����.

---

### `saturate()`
```php
saturate(): UXColor
```
���������� ����� ���������� ������ �����.

---

### `desaturate()`
```php
desaturate(): UXColor
```
���������� ����� ���������� ������ �����.

---

### `interpolate()`
```php
interpolate(UXColor $color, double $t): UXColor
```
���������� ����������������� ������ �����.

---

### `getRGB()`
```php
getRGB(): int
```
���������� ���� � ���� ������ ����� R, G, B.

---

### `getWebValue()`
```php
getWebValue(): string
```
������������� ����� � ���� HTML �����, ������ ������������ � `#`, �������� `#637DFAC`.

---

## ��������� ������

### `of()`
```php
of(string $colorString): UXColor
```
���������� ������ ����� ������ �� ���������� ������ (��� ����� ���� HTML ������ �����).

```php
$color = UXColor::of('#FD73AC');
```

---

### `rgb()`
```php
rgb(int $r, int $g, int $b, double $opacity = 1.0): UXColor
```
���������� ������ ����� ������ �� R,G,B ��������, ��� ������ �������� ��� ����� �� 0 �� 255.

```php
$color = UXColor::rgb(120, 76, 230);
```