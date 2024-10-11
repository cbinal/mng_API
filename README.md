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

