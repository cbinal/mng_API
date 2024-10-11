[Detaylı sorularınız için bana buradan ulaşabilirsiniz.](https://kayrem.com)

Öncelikle dosya import edilir.
* from dosya.yolu.Mng import Mng

Oluşturma:
* mng = Mng()

Kullanım:
* payload = {
                            "order": {
                                "referenceId": f"SIP0{order.id}111",
                                "barcode": f"SIP{order.id}",
                                "billOfLandingId": f"IRS {order.id}",
                                "isCOD": cod,
                                "codAmount": float(cod_amount),
                                "shipmentServiceType": 1,
                                "packagingType": 2 if content['desi'] == 1 and content['weight'] == 1 else 3,
                                "content": content['content'],
                                "smsPreference1": 1,
                                "smsPreference2": 0,
                                "smsPreference3": 0,
                                "paymentType": 1,
                                "deliveryType": 1,
                                "description": content['content'],
                                "marketPlaceShortCode": "",
                                "marketPlaceSaleCode": ""
                            },
                            "orderPieceList": [
                                {
                                "barcode": f"SIP{order.id}-1",
                                "desi": content['desi'],
                                "kg": content['weight'],
                                "content": "Açıklama"
                                }
                            ],
                            "recipient": {
                                "customerId": "",
                                "refCustomerId": "",
                                "cityCode": 0,
                                "cityName": order.delivery_city,
                                "districtName": order.delivery_state,
                                "districtCode": 0,
                                "address": order.delivery_address,
                                "bussinessPhoneNumber": "",
                                "email": order.email,
                                "taxOffice": "",
                                "taxNumber": "",
                                "fullName": f"{order.delivery_first_name} {order.delivery_last_name}",
                                "homePhoneNumber": "",
                                "mobilePhoneNumber": order.delivery_phone
                            }
                        }
                        shipping = mng.create_order(payload)
                        print(shipping)


Here's why:
* Your time should be focused on creating something amazing. A project that solves a problem and helps others
* deneme
* You shouldn't be doing the same tasks over and over like creating a README from scratch
* You should implement DRY principles to the rest of your life :smile:

Of course, no one template will serve all projects since your needs may be different. So I'll be adding more in the near future. You may also suggest changes by forking this repo and creating a pull request or opening an issue. Thanks to all the people have contributed to expanding this template!

Use the `BLANK_README.md` to get started.
