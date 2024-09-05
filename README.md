# terminal-webhook-dbg

1. Seadista Url, kuhu postitatakse
2. Vali format - jwsjson or openjson. openjson postitab avatud JSONi, jwsjson JWS 
3. jwsjson korral tuleb lisada JWK oct HS256, saab genereerida nt. https://mkjwk.org/
   
`
{
  "hooks": {
    "DirectoDelivery": [
      {
        "Name": "some",
        "Url": "https://www.vtmf.ee/tracking",
        "Format": "jwsjson",
        "Settings": {
          "kid": "pA9jkPnQ_KxBTsx2dDTsY137rALCu7FhtjwPVhx9d1A",
          "k": "BhJRj4zm7BGTrQwtldn68ZPTxIHwLWfNdUhbxaRp6wE"
        }
      }
    ]
  },
}
`

Edasi saab käsurealt käivitada parameetritega:
`--mode Test --ClientOrderNumber 23322 --DeliveryNumber 22323 --OrderNumber 22323 --TrackingUrl https://www.courier.com?xxx=yyyy --BookingReference DW2222`
