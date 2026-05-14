																┌──────────────────┐                       ┌──────────────────┐  6.1.1: «create»     ┌──────────────────┐
                                                                │    :Client       │                       │    :Campaign     │ ───────────────────► │   newAd:Advert   │
                                                                └─────────▲────────┘                       └─────────▲────────┘                      └──────────────────┘
                                                                          │                                          │
                                                                          │  1.1 *[For all clients]:                 │  2.2 *[For all client's campaigns]:
                                                                          │        getClientDetails()                │        getCampaignDetails()
                                                                          │  2.1: listCampaigns()                    │  4.1: listAdverts()
                                                                          │                                          │  6.1: createAdvert(data)
                                                                          │                                          │
                                                                                          1: findClients()
                                                                                          2: selectClient(c)
                                                                                          4: selectCampaign(camp)
                                                                                          6: addAdvert(camp, data)
    ┌──────────────────┐          ┌──────────────────┐                          ┌─────────────────────────────────────────────┐
    │ :CampaignManager │ ───────► │   :AddAdvertUI   │ ───────────────────────► │                :AddAdvert                   │
    └──────────────────┘          └──────────────────┘                          └─────────────────────┬───────────────────────┘
                                                                                                      │
                                                                                                      │  4.2 *[For all campaign's adverts]:
                                                                                                      │        getAdvertDetails()
                                                                                                      ▼
                                                                                            ┌──────────────────┐
                                                                                            │     :Advert      │
                                                                                            └──────────────────┘
