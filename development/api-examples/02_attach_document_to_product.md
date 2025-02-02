# Dokumentáció csatolása termékhez

Az alábbi példában bemutatásra kerül, hogy miként lehet dokumentumot feltölteni és azt a kiválasztott termékhez csatolni.

Fájlfeltöltéshez példa az alábbi [linken](https://support.shoprenter.hu/hc/hu/articles/215106038-F%C3%A1jlok-felt%C3%B6lt%C3%A9se-%C3%A9s-kezel%C3%A9se) olvasható.

### 1. lépés

A [File Resource](../../api/file.md) segítségével töltsük fel a kívánt dokumentumot. Fontos, hogy a request **body**-ban megadott **filePath** értékének adjuk meg a `srattached\/` mappát, illetve a **type** értéke mindenképp `image` legyen, mégha szöveges dokumentumról is van szó.

**filePath**: <strong>FIGYELEM!</strong> A feltöltendő fájlok csak az angol ABC betűit és (),_,-, karaktereket, illetve számokat tartalmazhatnak!

### Példa

#### Request

<table>
  <tr>
    <td><b>method:</b></td>
    <td>POST</td>
  </tr>
  <tr>
    <td><b>url:</b></td>
    <td>http://shopname.api.myshoprenter.hu/files</td>
  </tr>
  <tr>
    <td><b>headers:</b></td>
    <td>
        Accept:application/json<br>
        Content-Type:application/json
    </td>
  </tr>
</table>

```json
{
    "data": {
        "filePath": "srattached\/teszt.pdf",
        "type": "image",
        "attachment": "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IDI3OCA+PgpzdHJlYW0KeJxdkctuhCAUhvc8xVlOFxMYL2MXxmQ6tomLXlLbB1A4WpKKBHHh25eLnSYlgeQ/5/wf5Idem7pR0gJ9MzNv0cIglTC4zKvhCD2OUpFTAkJyu6tw8qnThDpzuy0Wp0YNMylLAPruuos1GxwuYu7xjtBXI9BINcLh89o63a5af+OEygIjVQUCB0d67vRLNyHQYDs2wvWl3Y7O8zfxsWmEJOhTfA2fBS6642g6NSIpmVsVlE9uVQSV+NfPoqsf+FdnwnTqphlLWOVVWgSVZ0Flj0GdH4LK66CKS+DuhPSXd7s+i4jsPnojKWeRm8RiHYvnWIyTRbpzI8k/3Ud8y4WvxrhIwj+ELHwKUuHtq/SsvcvvHyvGjSllbmRzdHJlYW0KZW5kb2JqCjEwIDAgb2JqCjw8IC9UeXBlIC9PYmpTdG0gL0xlbmd0aCA0ODEgL0ZpbHRlciAvRmxhdGVEZWNvZGUgL04gNiAvRmlyc3QgMzggPj4Kc3RyZWFtCnicfVJNj9owEL33V7wjHIg/gxNptRIspYsqdtFCu4cVBy9x06ghiRIjlX/fcWCB9lBZsZXxm3lv3lgIcAgJJSAU4hhCQxg6YkiRQoyhNf90dwe2auvssHMtButfhWWr2Rx7kwxxf99fT5dgT3W7tyXYzkJc4rZz87ryYJO2sOVyAzZz3c5Vma18uOjwFmg4XrAF+1zt6qyocrBF5ipf+OPoEWx9ePfHxoFtaOd01N+qgoAOaZ/Yx8F6njPvQ32gHwH2tcgCxYXhBF3Z3HUf2EnQ45HyOJJGaU3Ztnl0Rf7Tw4g4SiQnf866PUZSiCgVmo+JsrR5B33ink7r30Q1Go91FMfcJBgpqSPDDVeQXCaRokoQXJlI8FQlQU9InBelk0hOvYTAk927G8cW3pbFblLlpSMMW3u3/w5NwtJEU5Wb9oPGtmh83f5nAA+L2frYUZFF9aNGAD23mWuD7YMP24dgLy4vOt8eMZhk9bsbhjk0Ten2wQRO9ftKm/rLYra0zXVi5NRrkPmPHnpSfX+XYVJygATx8q8RsldykdNnYo6wpDFR0nu3DW+Upik4Bah7ChgBIyk8jkQslQbZ/oaYh7xEqYjTHATBaEviG1gyPsOuxa+XW6TqfL2lRVb+AScd2i1lbmRzdHJlYW0KZW5kb2JqCjEgMCBvYmoKPDwgL1R5cGUgL1hSZWYgL0xlbmd0aCAxNiAvRmlsdGVyIC9GbGF0ZURlY29kZSAvRGVjb2RlUGFybXMgPDwgL0NvbHVtbnMgNCAvUHJlZGljdG9yIDEyID4+IC9XIFsgMSAyIDEgXSAvU2l6ZSAyIC9JRCBbPDMyMmFhMzRmZmRiMWMxNjQwZWM5YmM3MGNiMzg3YTFhPjwzMjJhYTM0ZmZkYjFjMTY0MGVjOWJjNzBjYjM4N2ExYT5dID4+CnN0cmVhbQp4nGNiAAImRqcjDAACegEMCmVuZHN0cmVhbQplbmRvYmoKICAgICAgICAgICAgICAgCnN0YXJ0eHJlZgoyMTYKJSVFT0YK"
    }
}
```

#### Response

```json
{
    "filePath": "srattached/teszt.pdf",
    "type": "image"
}
```

### 2. lépés

Ezt követően az előbb feltöltött képhez a [Document Resource](../../api/document.md) segítségével egy azonosítót hozunk létre, amit legkönnyebben az alábbi request elküldésével tudunk megkapni.

### Példa

#### Request

<table>
  <tr>
    <td><b>method:</b></td>
    <td>POST</td>
  </tr>
  <tr>
    <td><b>url:</b></td>
    <td>http://shopname.api.myshoprenter.hu/documents</td>
  </tr>
  <tr>
    <td><b>headers:</b></td>
    <td>
        Accept:application/json<br>
        Content-Type:application/json
    </td>
  </tr>
</table>

```json
{
    "data": []
}
```

#### Response

```json
{
    "href": "http://shopname.api.myshoprenter.hu/documents/ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ==",
    "id": "ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ==",
    "innerId": "5",
    "dateCreated": "2019-09-11T15:12:47",
    "dateUpdated": "2019-09-11T15:12:47"
}
``` 

### 3. lépés

A Document resource ID birtokában, a [Document Description Resource](../../api/document_description.md) segítségével beállíthatjuk a feltöltött dokumentum nevét és nyelvét. A nyelvet a [Language Resource](../../api/language.md) segítségével tudjuk lekérdezni. Megjegyzés: a **filename** és a **mask** értékének nem kell megegyezni.

### Példa

#### Request

<table>
  <tr>
    <td><b>method:</b></td>
    <td>POST</td>
  </tr>
  <tr>
    <td><b>url:</b></td>
    <td>http://shopname.api.myshoprenter.hu/documentDescriptions</td>
  </tr>
  <tr>
    <td><b>headers:</b></td>
    <td>
        Accept:application/json<br>
        Content-Type:application/json
    </td>
  </tr>
</table>

```json
{
    "data": {
        "name": "Teszt pdf neve",
        "filename": "teszt.pdf",
        "mask": "teszt.pdf",
        "document": {
            "id": "ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ=="
        },
        "language": {
            "id": "bGFuZ3VhZ2UtbGFuZ3VhZ2VfaWQ9MQ=="
        }
    }
}
```

#### Response

```json
{
    "href": "http://shopname.api.myshoprenter.hu/documentDescriptions/ZG9jdW1lbnREZXNjcmlwdGlvbi1kb2N1bWVudF9pZD01Jmxhbmd1YWdlX2lkPTE=",
    "id": "ZG9jdW1lbnREZXNjcmlwdGlvbi1kb2N1bWVudF9pZD01Jmxhbmd1YWdlX2lkPTE=",
    "name": "Teszt pdf neve",
    "filename": "test.pdf",
    "mask": "test.pdf",
    "document": {
        "href": "http://shopname.api.myshoprenter.hu/documents/ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ=="
    },
    "language": {
        "href": "http://shopname.api.myshoprenter.hu/languages/bGFuZ3VhZ2UtbGFuZ3VhZ2VfaWQ9MQ=="
    }
}
```

### 4. lépés

Ha mindez megvan, akkor a [Product Document Relation Resource](../../api/product_document_relation.md) segítségével a kívánt termékhez tudjuk csatolni a feltöltött dokumentumot. A terméket a [Product Resource](../../api/product.md) segítségével tudjuk lekérdezni. 

### Példa

#### Request

<table>
  <tr>
    <td><b>method:</b></td>
    <td>POST</td>
  </tr>
  <tr>
    <td><b>url:</b></td>
    <td>http://shopname.api.myshoprenter.hu/productDocumentRelations</td>
  </tr>
  <tr>
    <td><b>headers:</b></td>
    <td>
        Accept:application/json<br>
        Content-Type:application/json
    </td>
  </tr>
</table>

```json
{
    "data": {
        "product": {
            "id": "cHJvZHVjdC1wcm9kdWN0X2lkPTE2OQ=="
        },
        "document": {
            "id": "ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ=="
        }
    }
}
```

#### Response

```json
{
    "href": "http://shopname.api.myshoprenter.hu/productDocumentRelations/cHJvZHVjdERvY3VtZW50LWlkPTY=",
    "id": "cHJvZHVjdERvY3VtZW50LWlkPTY=",
    "product": {
        "href": "http://shopname.api.myshoprenter.hu/products/cHJvZHVjdC1wcm9kdWN0X2lkPTE2OQ=="
    },
    "document": {
        "href": "http://shopname.api.myshoprenter.hu/documents/ZG9jdW1lbnQtZG9jdW1lbnRfaWQ9NQ=="
    }
}
```
