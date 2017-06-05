# UXImage

- **class** `UXImage` (`php\gui\UXImage`)
- **package** `gui`

```php
use php\gui\UXImage;
```

����� ��������, ������� ������ ����������� � ������, � ��� ����� � ��� GUI �����������. ������ ����� ��� �� �������� ���������� �����������. 
> ���� ��� ����� ����� ����������� ���������� "�����������", �������� [UXImageView](UXImageView) ��� [UXImageArea](UXImageArea).

#### ��������
- `->`[`width`](#width-double) - _������_
- `->`[`height`](#height-double) - _������_
- `->`[`progress`](#progress-double) - _�������� ��������_

#### ��������� ������
 - `UXImage ::`[`ofUrl()`](#ofurl) - _������� ����������� �� URL_

#### ������
 - [����������� (`new`)](#__construct) `__construct` - _�������� �����������_
 - `->`[`getPixelColor()`](#getpixelcolor) - _���� �������_
 - `->`[`getPixelARGB()`](#getpixelargb) - _���� ������� � ARGB_
 - `->`[`cancel()`](#cancel) - _������ ��������_
 - `->`[`isError()`](#iserror) - _������ ��������_
 - `->`[`isBackgroundLoading()`](#isbackgroundloading) - _������� �� ��������_
 - `->`[`save()`](#save) - _���������� �����������_

---

## ��������

### `width` (double)
������ ����������� � ��������.

---

### `height` (double)
������ ����������� � ��������.

---

### `progress` (double)
�������� �������� ����������� �� 0 �� 1, ��� 1 - ��� 100%.

---

## ������

### `__construct()`
```php
__construct(Stream|string $stream [, bool $requiredWidth, bool $requiredHeight, $proportional = true])
```

```php
$image = new UXImage('path/to/image.png');
```

---

### `getPixelColor()`
```php
getPixelColor(int $x, int $y): UXColor
```
���������� ���� ������� ����������� �� `x, y`, ��������� ������ ������ [UXColor](UXColor).

---

### `getPixelARGB()`
```php
getPixelARGB(int $x, int $y): int
```
���������� ���� ������� ����������� �� `x, y` � ���� ������ �����, alpha ������������ ������ � ��� �������� ������ � R, G � B.

---

### `cancel()`
�������� �������� �����������, ��������� ��� ������� �������� ����������� �� url.

---

### `isError()`
```php
isError(): bool
```
���������� `true` ���� ��� �������� ����������� ��������� ������, ��������, ������ ����������� ��������. 

---

### `isBackgroundLoading()`
```php
isBackgroundLoading(): bool
```
���������� `true` ���� ����������� ��� �����������, ��������� ��� ������� �������� ����������� �� url.

---

### `save()`
```php
save(Stream|string $to, string $format = 'png')
```
��������� ����������� � ���� ��� ����� (Stream) � ������� `$format`. �������������� �������:
- `png`
- `jpg`, `jpeg`
- `gif`

```php
$image->save('path/to/image.jpg', 'jpg');
```

---

## ��������� ������

### `ofUrl()`
```php
UXImage::ofUrl(string $url, bool $background = false): UXImage  
```
��������� ����������� �� url.

```php
// ������� �������� �����������, $background - true
$image = UXImage::ofUrl('http://example.com/image.png', true); 
```