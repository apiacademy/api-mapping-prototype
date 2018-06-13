# Simple Editing/Evolving/Exporting Example

Starting from our Slack discussion, here a simple example of how I see API maps being used, being evolved, and how exporting them for documentation fits into the picture.

I start with a simple set of resources, in this case a API to search a product catalog. The model ideas shown here already are that the search results are a collection (which could be a specifically supported type of resource), and the product resource is a set of resources (as indicated by the URI template).

This is the starting point of the API and already could yield some OpenAPI. From the API map point of view, what is missing so far are links that connect the resources in navigable ways.

![Just Resources](resources.jpg)

Next some links are added. These links must have types, and these types should be used according to *Web Linking*. These links turn the resource view into an actual API map.

This could already be exported as a sketch. If it were exported as a navigable HTML map at `http://example.com/sketch`, then it should have working anchors such as `http://example.com/sketch#product` or `http://example.com/sketch/resource/product` which would represent the product resource of the sketch. These URIs should remain stable, and they can then be used to be linked from other resources, such as the OpenAPI description.

![Adding Links](links.jpg)

Some details may be added which would not change the overall set of entities in the API map (same set of resources and links), but more details are added, as the API map is fleshed out a bit.

Re-exporting this API map should simply replace the export the HTML with updated HTML with the added API details. The URIs for the API map entities (resources and links) should remain stable. This means that anybody looking at the older and less detailed maps now simply would get the newer and more detailed version.

![More Details](details.jpg)

If a new resource gets added, that evolves the API map to have a new entity (the product detail resource type). This evolves the API in a backwards-compatible way: All the previously existing resources and links still exist, but there is now one more resource.

When exporting this updated API map, there now should be a new linkable resource that may be `http://example.com/sketch#detail` or `http://example.com/sketch/resource/detail`, but most importantly, the previously existing links `http://example.com/sketch#product` or `http://example.com/sketch/resource/product` should still work. The only difference for the product resource that it now would say that a product must/can provide a `detail` link, but that, too, would be a backwards-compatible change to the API.

![Adding Resources](added-resource.jpg)

Finally, when adding interlinking to the API map, the existing API map entities for resources and links once again should remain stable, only that now there might be more links showing up, because for example now the search results are a pageable collection. That would change the definition of how the `http://example.com/sketch#search-results` or `http://example.com/sketch/resource/search-results` works, but once again would not change the identifier of that resource in the exported HTML version of the API map.

![Adding Links](added-links.jpg)

This progression of editing and API evolution and exporting of the API map demonstrates how the API map can evolve, how that is supported through incremental refinements and additions to the API map, and how this should be supported by an export process that always to export an API map, and that makes sure that the identity of API map entities remains stable.
