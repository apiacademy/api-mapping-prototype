# API Map Data Model

We need a data model for how sketches are working. For the initial MVP, we want a minimal model for the sketch. It should capture the essentials of modeling hypermedia APIs, have some similarities with how site maps work, and have potential value for the sketching and documentation tasks.

## Resources

* Name
* URI
* Properties (optional, probably as name/value pairs, at least initially)
* Collection (should be marked as special types of resources as a common resource pattern)

## Links

* Relation type
* Occurrences
* Target
* Essential (not quite clear how to best define this, but it might be useful to have a way to distinguish links that are essential to the API workflow, and those that are secondary, this could potentially help a lot with uncluttering the visualization)
