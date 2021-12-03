## Algolia implementation in Agriaku

## Adapters

### accessor/algolia/AlgoliaAccessorModule
To inject the ProductInventorySummaryAlgoliaAccessorImpl to the accessor module

### accessor/algolia/ProductInventorySummaryAlgoliaAccessorImpl
- what is categoryIdsToBeFetched doing?
- what is HashSet and HashMap for?
- what is getByFilter for?
- what is convertToListOfUrl for?

### api/algolia/AlgoliaAPIModule
To inject the SyncToAlgoliaAPIRoute to the APIModule

### api/algolia/AlgoliaAPITag
To group the algolia-related endpoint/s in swagger

### api/algolia/SyncToAlgoliaAPIRoute
To sync inventory to algolia

### service/algolia/AgriakuAlgoliaClient
Contains BindingAnnotation for AgriakuAlgoliaClient, to be used in AlgoliaServiceImpl as an instance

### service/algolia/AlgoliaModule
To inject AlgoliaServiceImpl to the AlgoliaService, as well as creating a client instance annotated with AgriakuAlgoliaClient

### service/algolia/AlgoliaServiceImpl
- why use ArrayList? TO CREATE A MUTABLE LIST
- what are these algolia methods? setAttributesToRetrieve, setHitsPerPage, setPage, setDistinct, setRanking, setAttributeForDistinct, setSearchableAttributes
- what is ArrayList<Deferred<Any>>() used for?


