[![ImageBoss logo](https://service.imageboss.me/width/180/https://imageboss.me/emails/logo-2@2x.png)](https://imageboss.me)

# ImageBoss Helper for Python

Unofficial package for generating ImageBoss URLs.
[https://imageboss.me/](https://imageboss.me/)

**Table of Contents**
- [ImageBoss Helper for Python](#imageboss-helper-for-python)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Example `Image Resizing With Cover Operation`](#example-image-resizing-with-cover-operation)
    - [Example `Image Resizing With Height Operation`](#example-image-resizing-with-height-operation)
    - [Example `Image Resizing With Extra Options`](#example-image-resizing-with-extra-options)
    - [All operations and options for Image Resizing](#all-operations-and-options-for-image-resizing)
    - [Disabling URL generation](#disabling-url-generation)
  - [Tested on](#tested-on)

## Installation
Add this line to your application's requirements.txt:
```
imageboss
```

Or install it yourself as:

```
pip install imageboss
```

## Usage
### Example `Image Resizing With Cover Operation`
```python
from imageboss import ImageBoss

client = ImageBoss.Client('https://mywebsite.com')

image_url = client.path('/images/img01.jpg').operation('cover', width=100, height=100)

#=> https://service.imageboss.me/cover/100x100/https://mywebsite.com/images/img01.jpg
```

### Example `Image Resizing With Height Operation`
```python
from imageboss import ImageBoss

client = ImageBoss.Client('https://mywebsite.com')

image_url = client.path('/images/img01.jpg').operation('height', height=100)

#=> https://service.imageboss.me/height/100/https://mywebsite.com/images/img01.jpg
```

### Example `Image Resizing With Extra Options`
```python
from imageboss import ImageBoss

client = ImageBoss.Client('https://mywebsite.com')

image_url = client.path('/images/img01.jpg').operation('width', width=100, options={'grayscale': true})

#=> https://service.imageboss.me/width/100/grayscale:true/https://mywebsite.com/images/img01.jpg
```
### All operations and options for Image Resizing
It's all available on our [Official Docs](https://imageboss.me/docs).

### Disabling URL generation
If you are coding on `test`, `development` environments and don't want to send any image to ImageBoss
you can always disable the URL generation and the client will just fallback to the original path provided.

```python
from imageboss import ImageBoss

client = ImageBoss.Client('https://mywebsite.com')

image_url = client.path('/images/img01.jpg').operation('width', width=100, options={'grayscale': true})

#=> /images/img01.jpg
```
This will give you the ability to see your image without adding extra code to handle this situation.

## Tested on
Python
  - 2.7.14
  - 3.6.5
