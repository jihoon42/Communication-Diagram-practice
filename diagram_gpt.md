```
+-------------------+        +----------------------+        +-------------+
| :CampaignManager  |------->| :AddAdvertBoundary   |------->| :AddAdvert  |
+-------------------+        +----------------------+        +-------------+
        2: selectClient(client)             2.1: selectClient(client)        |\
        4: selectCampaign(campaign)         4.1: selectCampaign(campaign)    | \
        6: submitAdvertData(advertData)     6.1: createAdvert(advertData)    |  \
                                                                            |   \ 1: *[for all clients]: getClient()
                                                                            |    \ 3: getCampaigns()
                                                                            |     v
                                                                            |  +-------------+
                                                                            |  | :Client     |
                                                                            |  +-------------+
                                                                            |        \
                                                                            |         \ 3.1 *[for campaigns of client]: getCampaign()
                                                                            |          v
                          5: getAdverts()                                   |  +-------------+
                          6.2: addAdvert(advertData)                        |  | :Campaign   |
                                                                            v  +-------------+
                                                                               /       \
                                                                              /         \ 6.2.1: create(advertData)
                                                                             /           v
                                                                            /     +------------------+
                                                                           /      | newAdvert:Advert |
                                                                          /       +------------------+
                                                                         /
                                                                        / 5.1 *[for adverts of campaign]: getAdvert()
                                                                       v
                                                                 +-------------+
                                                                 | :Advert     |
                                                                 +-------------+
```
