---
description: Item Approval
---

# Onay Verme

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/approve.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

{% hint style="info" %}
Pazaryeri çözümünde, ödeme iyzico’dan geçtikten sonra, üye işyeri ödeme içinde yer alan kırılıma / ürüne onay verene dek para korumalı havuz hesapta bekletilir. Üye işyeri bu sürede ödemeyi iptal edebilir, ödemenin kırılımını iade edebilir ya da ürün alıcıya ulaştı ve işlem sorunsuz tamamlandıysa para transferi için ürüne onay verebilir veya verdiği ürün onayını geri çekebilir.

Ürüne onay vermek için ödeme kırılımına ait id \(paymentTransactionId\) iletilmesi gerekmektedir. Onay verilen ödeme kırılımı id’si \(paymentTransactionId\) servisten döner.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **paymentTransactionId** | string | evet | Ödeme kırılımına ait ürünün iyzico taradından belirlenmiş unique id'si. |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşmesi yapmak için kullanılabilir. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **paymentTransactionId** | string | Ödeme kırılımına ait ürünün iyzico taradından belirlenmiş unique id'si. |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr**dir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470733388749,
    "conversationId": "123456789",
    "paymentTransactionId": "38248"
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/approve.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/ApproveSample.cs#L10)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/ApproveSample.java#L11)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/approval_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/approve.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L24)

