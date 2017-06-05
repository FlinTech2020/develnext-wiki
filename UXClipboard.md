# UXClipboard

- **class** `UXClipboard` (`php\gui\UXClipboard`)
- **package** `gui`

```php
use php\gui\UXClipboard;
// ���
use gui;
```

����������� ����� ��� ������ � ������� ������ ������� (������� ����������� � ������� � ������ ���� ��). ����� ����� ������ ��������� ������, ���������� ������� ������ ������� ������.

---

#### ��������� ������

- `UXClipboard ::`[`clear()`](#clear) - _������� ������_
- `UXClipboard ::`[`getText()`](#gettext) - _�������� ����� �� ������_
- `UXClipboard ::`[`setText()`](#settext) - _�������� ����� � �����_
- `UXClipboard ::`[`setContent()`](#setcontent) - _�������� ������� � �����_
- `UXClipboard ::`[`getImage()`](#getimage) - _�������� ����������� �� ������_
- `UXClipboard ::`[`getFiles()`](#getfiles) - _�������� ���� � ������ �� ������_
- `UXClipboard ::`[`getHtml()`](#gethtml) - _�������� html �� ������_
- `UXClipboard ::`[`getUrl()`](#geturl) - _�������� ������ �� ������_
- `UXClipboard ::`[`hasText()`](#hastext) - _���� �� ����� � ������_
- `UXClipboard ::`[`hasImage()`](#hasimage) - _���� �� ����������� � ������_
- `UXClipboard ::`[`hasFiles()`](#hasfiles) - _���� �� ���� � ������ � ������_
- `UXClipboard ::`[`hasHtml()`](#hashtml) - _���� �� html � ������_

---

## ��������� ������

### `clear()`
�������� ����� ������ �� ����� ������.

```php
// ������� ������
UXClipboard::clear();
```

---

### `getText()`
```php
UXClipboard::getText(): string
```
����� ���������� ����� �� ������ ������, ���� ��� ��� ���, ���������� `null`.

```php
// �������� ����� �� ������ ������
alert(UXClipboard::getText());
```

---

### `setText()`
```php
UXClipboard::setText(string $text)
```
����� �������� ����� `$text` � ����� ������.

```php
// ��������� ����� � ����� ������.
UXClipboard::setText('Hello World');
```

> :information_source: �������� ����� ����� [`setContent()`](#setcontent).

---

### `setContent()`
```php
UXClipboard::setContent(array $content)
```
����� �������� ������������� ������� (�����, �����������, ����� � �.�.) � ����� ������. � ������� `$content` ��� ���������� ������� ���������� ������ �������: `text` ��� �����, `image` ��� ����������� ������ [UXImage](UXImage), `files` ��� ������ ����� � ������ � ���� ������� ��� ���������, `html` ��� html, `url` ��� ������.

```php
UXClipboard::setContent([
     'files' => ['path/to/file1.png', 'path/to/file2.png'],
     'text' => 'foobar text',
     'url' => 'http://develnext.org',
     'html' => '<b>World</b>',
     'image' => new UXImage('path/to/image.png')
]);
```

---

### `getImage()`
```php
UXClipboard::getImage(): UXImage
```
����� ���������� ����������� �� ������ ������ � ���� ������� [UXImage](UXImage).

```php
// ��������� ����������� �� ������ � ��������� �����������.
$this->clipImage->image = UXClipboard::getImage();
```

---

### `getFiles()`
```php
UXClipboard::getFiles(): array
```
����� ���������� ������ ����� � ������ �� ������ ������. 

> :information_source: ����������� ������ � ��������� �� ���������� ����� ��������� �� ������ ����� � ����� ������.

```php
$files = UXClipboard::getFiles();
print_r($files);
```