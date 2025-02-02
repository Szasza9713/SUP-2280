# WebHook Resource

## Tulajdonságok

<ResourceProperties :resource="'webhook'" :lang="'hu'"/>

## Endpoints

[//]: <> (GET ENDPOINT)
<ResourceEndpoint :resource="'webhook'" :endpoint="'get'" :lang="'hu'">

<template v-slot:responseJSON>

<<< @/docs/fixtures/api/webhook/response/json/get_id.json

</template>

<template v-slot:responseXML>

<<< @/docs/fixtures/api/webhook/response/xml/get_id.xml

</template>

</ResourceEndpoint>

[//]: <> (GETCOLLECTION ENDPOINT)
<ResourceEndpoint :resource="'webhook'" :endpoint="'getCollection'" :lang="'hu'">

<template v-slot:responseJSON>

<<< @/docs/fixtures/api/webhook/response/json/get_page.json

</template>

<template v-slot:responseXML>

<<< @/docs/fixtures/api/webhook/response/xml/get_page.xml

</template>

</ResourceEndpoint>

[//]: <> (POST ENDPOINT)
<ResourceEndpoint :resource="'webhook'" :endpoint="'post'" :lang="'hu'">

<template v-slot:request>

<<< @/docs/fixtures/api/webhook/request/post.json

</template>

<template v-slot:responseJSON>

<<< @/docs/fixtures/api/webhook/response/json/get_id.json

</template>

<template v-slot:responseXML>

<<< @/docs/fixtures/api/webhook/response/xml/get_id.xml

</template>

</ResourceEndpoint>

[//]: <> (PUT ENDPOINT)
<ResourceEndpoint :resource="'webhook'" :endpoint="'put'" :lang="'hu'">

<template v-slot:request>

<<< @/docs/fixtures/api/webhook/request/put.json

</template>

<template v-slot:responseJSON>

<<< @/docs/fixtures/api/webhook/response/json/get_id.json

</template>

<template v-slot:responseXML>

<<< @/docs/fixtures/api/webhook/response/xml/get_id.xml

</template>

</ResourceEndpoint>

[//]: <> (DELETE ENDPOINT)
<ResourceEndpoint :resource="'webhook'" :endpoint="'delete'" :lang="'hu'"/>

## Fields property használata

Szabályozni tudjuk, mely mezőket küldje el a Shoprenter az egyes események bekövetkeztének pillanatában.
Ehhez webHookParameters **fields** propertyjében kell átadnunk egy tömbben a kívánt mezőneveket.

A következő táblázat tartalmazza az összes megadható mezőnevet, illetve azt, hogy egyes eseménytípusoknál, melyik adat érhető el.

### A megrendeléshez kapcsolódó események mezői
| Mező neve                      | Rendelés státusz váltás (order_confirm) |Új rendelés leadás (order_status_change)| Leírás                                                                                                                                                                                                                                                                                                                                                            |
|:-------------------------------|:---------------------------------------:| :---: |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| order_storeName                |                    x                    |x| Bolt név                                                                                                                                                                                                                                                                                                                                                          |
| order_innerId                  |                    x                    |x| Rendelés Belső Id                                                                                                                                                                                                                                                                                                                                                 |
| order_innerResourceId          |                    x                    |x| Rendelés Belső Resource Id-ja                                                                                                                                                                                                                                                                                                                                     |
| order_outerResourceId          |                    x                    |x| Rendelés Outer Id-ja                                                                                                                                                                                                                                                                                                                                              |
| order_firstname                |                    x                    |x| A Vevő keresztneve                                                                                                                                                                                                                                                                                                                                                |
| order_lastname                 |                    x                    |x| A Vevő vezetékneve                                                                                                                                                                                                                                                                                                                                                |
| order_phone                    |                    x                    |x| A Vevő telefonszáma                                                                                                                                                                                                                                                                                                                                               |
| order_fax                      |                    x                    |x| A Vevő fax száma                                                                                                                                                                                                                                                                                                                                                  |
| order_email                    |                    x                    |x| A Vevő email címe                                                                                                                                                                                                                                                                                                                                                 |
| order_email_hash               |                    x                    |x| A Vevő email címének sha256-al hashelt változata                                                                                                                                                                                                                                                                                                                  |
| order_cart_token               |                    x                    |x| A kosár tokenje, amelyet megvásároltak ebben a rendelésben                                                                                                                                                                                                                                                                                                        |
| order_shippingFirstname        |                    x                    |x| Szállítási Cím: Keresztnév                                                                                                                                                                                                                                                                                                                                        |
| order_shippingLastname         |                    x                    |x| Szállítási Cím: Vezetéknév                                                                                                                                                                                                                                                                                                                                        |
| order_shippingCompany          |                    x                    |x| Szállítási Cím: Cég név                                                                                                                                                                                                                                                                                                                                           |
| order_shippingAddress1         |                    x                    |x| Szállítási Cím: Cím 1                                                                                                                                                                                                                                                                                                                                             |
| order_shippingAddress2         |                    x                    |x| Szállítási Cím: Cím 2                                                                                                                                                                                                                                                                                                                                             |
| order_shippingCity             |                    x                    |x| Szállítási Cím: Város                                                                                                                                                                                                                                                                                                                                             |
| order_shippingCountryName      |                    x                    |x| Szállítási Cím: Ország neve                                                                                                                                                                                                                                                                                                                                       |
| order_shippingZoneName         |                    x                    |x| Szállítási cím: A földrajzi zóna neve                                                                                                                                                                                                                                                                                                                             |
| order_shippingPostcode         |                    x                    |x| Szállítási Cím: Irányítószám                                                                                                                                                                                                                                                                                                                                      |
| order_expectedDeliveryDate     |                    x                    | | Várható kiszállítás dátuma (Y-m-d)                                                                                                                                                                                                                                                                                                                                |
| order_paymentFirstname         |                    x                    |x| Számlázási Cím: Keresztnév                                                                                                                                                                                                                                                                                                                                        |
| order_paymentLastname          |                    x                    |x| Számlázási Cím: Vezetéknév                                                                                                                                                                                                                                                                                                                                        |
| order_paymentCompany           |                    x                    |x| Számlázási Cím: Cég név                                                                                                                                                                                                                                                                                                                                           |
| order_paymentAddress1          |                    x                    |x| Számlázási Cím: Cím 1                                                                                                                                                                                                                                                                                                                                             |
| order_paymentAddress2          |                    x                    |x| Számlázási Cím: Cím 2                                                                                                                                                                                                                                                                                                                                             |
| order_paymentCity              |                    x                    |x| Számlázási Cím: Város                                                                                                                                                                                                                                                                                                                                             |
| order_paymentCountryName       |                    x                    |x| Számlázási Cím: Ország neve                                                                                                                                                                                                                                                                                                                                       |
| order_paymentZoneName          |                    x                    |x| Számlázási cím: A földrajzi zóna neve                                                                                                                                                                                                                                                                                                                             |
| order_paymentPostcode          |                    x                    |x| Számlázási Cím: Irányítószám                                                                                                                                                                                                                                                                                                                                      |
| order_paymentTaxnumber         |                    x                    |x| Számlázási Cím: Adószám                                                                                                                                                                                                                                                                                                                                           |
| order_shippingMethodName       |                    x                    |x| Szállítási mód neve. Azon nyelven fog megjelenni, amilyen nyelven leadták a rendelést                                                                                                                                                                                                                                                                             |
| order_shippingMethodCode       |                    x                    | | Szállítási mód belső kódja                                                                                                                                                                                                                                                                                                                                        |
| order_shippingNetPrice         |                    x                    |x| A szállítás nettó ára                                                                                                                                                                                                                                                                                                                                             |
| order_shippingGrossPrice       |                    x                    |x| A szállítás bruttó ára                                                                                                                                                                                                                                                                                                                                            |
| order_shippingInnerResourceId  |                    x                    |x| A szállítási mód resource id-ja                                                                                                                                                                                                                                                                                                                                   |
| order_shippingCountryIsoCode2  |                    x                    | | A rendelés cél országának ISO kódja                                                                                                                                                                                                                                                                                                                               |
| order_paymentMethodName        |                    x                    |x| Fizetési mód neve. Azon nyelven fog megjelenni, amilyen nyelven leadták a rendelést                                                                                                                                                                                                                                                                               |
| order_paymentMethodCode        |                    x                    | | Fizetési mód belső kódja                                                                                                                                                                                                                                                                                                                                          |
| order_paymentNetPrice          |                    x                    |x| Fizetési módhoz tartozó nettó ár                                                                                                                                                                                                                                                                                                                                  |
| order_paymentGrossPrice        |                    x                    |x| Fizetési módhoz tartozó bruttó ár                                                                                                                                                                                                                                                                                                                                 |
| order_couponCode               |                    x                    |x| Kupon kód, amelyet felhasználtak a rendeléshez                                                                                                                                                                                                                                                                                                                    |
| order_couponGrossPrice         |                    x                    |x| Kupon bruttó összege                                                                                                                                                                                                                                                                                                                                              |
| order_cartAmountDiscount       |                    x                    |x| Mennyiségi árkedvezmény értéke. A szám negatív előjelű                                                                                                                                                                                                                                                                                                            |
| order_languageId               |                    x                    |x| A rendelés nyelvének belső id-ja                                                                                                                                                                                                                                                                                                                                  |
| order_languageCode             |                    x                    |x| A rendelés nyelvének ISO 2-es kódja                                                                                                                                                                                                                                                                                                                               |
| order_comment                  |                    x                    |x| A rendeléshez, a Vevő által írt megjegyzés                                                                                                                                                                                                                                                                                                                        |
| order_total                    |                    x                    |x| Rendelés nettó végösszege                                                                                                                                                                                                                                                                                                                                         |
| order_totalGross               |                    x                    |x| Rendelés bruttó végösszege                                                                                                                                                                                                                                                                                                                                        |
| order_taxPrice                 |                    x                    |x| Rendelés áfa tartalma                                                                                                                                                                                                                                                                                                                                             |
| order_currency                 |                    x                    |x| Rendelés pénznemének kódja                                                                                                                                                                                                                                                                                                                                        |
| order_newsletterChecked        |                                         |x| Hírlevél feliratkozás megtörtént-e?                                                                                                                                                                                                                                                                                                                               |
| order_reloadLink               |                    x                    |x| A rendelés újratöltő linke, elhagyott kosár esetén                                                                                                                                                                                                                                                                                                                |
| orderHistory_status            |                    x                    |x| A rendelés jelenlegi státuszának belső id-ja                                                                                                                                                                                                                                                                                                                      |
| orderHistory_statusText        |                    x                    |x| A rendelés jelenlegi státuszának szöveges reprezentációja                                                                                                                                                                                                                                                                                                         |
| orderHistory_comment           |                    x                    |x| A rendelés státuszához írt megyjegyzés                                                                                                                                                                                                                                                                                                                            |
| orderCreditCard_date           |                    x                    | | Bankkártyával fizetett rendelés: Fizetés dátuma                                                                                                                                                                                                                                                                                                                   |
| orderCreditCard_transactionId  |                    x                    | | Bankkártyával fizetett rendelés: Tranzakció azonosító                                                                                                                                                                                                                                                                                                             |
| orderCreditCard_licenceNumber  |                    x                    | | Bankkártyával fizetett rendelés: Engedély szám                                                                                                                                                                                                                                                                                                                    |
| orderCreditCard_bankAnswerCode |                    x                    | | Bankkártyával fizetett rendelés: Banki válaszkód                                                                                                                                                                                                                                                                                                                  |
| orderCreditCard_bankAnswer     |                    x                    | | Bankkártyával fizetett rendelés: Bank válasza                                                                                                                                                                                                                                                                                                                     |
| orderProduct_innerId           |                    x                    |x| Rendelt termék belső id-ja (Nem egyenlő a Termék id-val)                                                                                                                                                                                                                                                                                                          |
| orderProduct_innerResourceId   |                    x                    |x| Rendelt termék resource id-ja (Nem egyenlő a Termék reource id-val)                                                                                                                                                                                                                                                                                               |
| orderProduct_outerResourceId   |                    x                    |x| Rendelt termék outer id-ja (Nem egyenlő a Termék outer id-val)                                                                                                                                                                                                                                                                                                    |
| orderProduct_name              |                    x                    |x| Rendelt termék neve                                                                                                                                                                                                                                                                                                                                               |
| orderProduct_sku               |                    x                    |x| Rendelt termék cikkszáma                                                                                                                                                                                                                                                                                                                                          |
| orderProduct_price             |                    x                    |x| Rendelt termék nettó ára                                                                                                                                                                                                                                                                                                                                          |
| orderProduct_currency          |                    x                    |x| Rendelt termék árának pénzneme                                                                                                                                                                                                                                                                                                                                    |
| orderProduct_taxRate           |                    x                    |x| Rendelt termék ÁFA mértéke (pl.: 27% ÁFA-nál 27.000)                                                                                                                                                                                                                                                                                                              |
| orderProduct_quantity          |                    x                    |x| Rendelt termék mennyisége                                                                                                                                                                                                                                                                                                                                         |
| orderProduct_image             |                    x                    |x| Rendelt termék termék képének url-je                                                                                                                                                                                                                                                                                                                              |
| orderProduct_category          |                    x                    |x| Rendelt termék kategóriái, vesszővel elválasztva                                                                                                                                                                                                                                                                                                                  |
| orderProduct_volume            |                    x                    |x| Rendelt termék térfogatra vonatkozó adatai:<br>**height**: Magasság<br>**width**: Szélesség  <br> **length**: Hosszúság  <br> **volumeUnit**: Mértékegység adatok {  <br> **unit**: A mértékegység, amelyben ki van fejezve a térfogat  <br>**language**: A mértékegység nyelvének ISO 3-as kódja (Magyar nyelven pl. cm-ben jelennek meg a térfogat adatok)<br>} |
| orderProduct_weight            |                    x                    |x| Rendelt termék súly adatai: <br> **weight**: Súly érték <br> **weightUnit**: Súly adatok {<br>**unit**: A mértékegység, amelyben ki van fejezve a súly<br>**language**: A súly nyelvének ISO 3-as kódja (Magyar nyelven pl. kg-ban jelennek meg a súly adat)<br>}                                                                                                 |
| orderProductOption_name        |                    x                    |x| A termékhez rendelt változat képző paraméter neve                                                                                                                                                                                                                                                                                                                 |
| orderProductOption_valueName   |                    x                    |x| A termékhez rendelt változat képző paraméter értéke                                                                                                                                                                                                                                                                                                               |
| orderProductOption_price       |                    x                    |x| Az ármódosítás mértéke nettóban.                                                                                                                                                                                                                                                                                                                                  |
| orderProductOption_prefix      |                    x                    |x| Az ármodosítás előjele (+ vagy -)                                                                                                                                                                                                                                                                                                                                 |

### A hírlevélhez kapcsolódó események mezői
| Mező neve                 | newsletter_subscribe | newsletter_unsubscribe | newsletter_update_subscriber | Leírás                                      |
|:--------------------------|:--------------------:|:----------------------:|:----------------------------:|---------------------------------------------|
| subscriber_id             |          x           |           x            |              x               | Feliratkozó azonosítója                     |
| subscriber_firstname      |          x           |           x            |              x               | Vezetéknév                                  |
| subscriber_lastname       |          x           |           x            |              x               | Keresztnév                                  |
| subscriber_email          |          x           |           x            |              x               | E-mail cím                                  |
| subscriber_phone          |          x           |           x            |              x               | Telefonszám                                 |
| subscriber_status         |          x           |           x            |              x               | Státusz                                     |
| subscriber_language       |          x           |           x            |              x               | A feliratkozás nyelvének azonosítója        |
| subscriber_hash           |          x           |           x            |              x               | Aktiváláshoz, leiratkozáshoz szükséges hash |
| subscriber_subscribe_date |          x           |           x            |              x               | Feliratkozás dátuma                         |

## Példák

- [**"Új rendelés feladás" webhook működése**](../development/api-examples/06_webhook.md)
