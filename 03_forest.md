# Ontological Forest

Following model is trying to show our model as a forest where trees are formed by different principles of identity, enclose *sortals*, and are interconected with relations and *non-sortals*. But you can see those trees as houses as well... And by the way this one is simpler than with partitions!

* First lets draw roots as triangles (roots or roofs if you prefer to imagine it as houses). Each root/roof for one *kind* and principle of identity.

![Kinds and identity][forest_kinds]

* Now lets add other *sortals* which belongs under each of those root/roofs.

![Other sortals][forest_sortals]

* Without *non-sortals* only way how to connect different trees/houses is by relations. We have three: *submits*, *supervises*, and *performs*.

![Relations][forest_relations]

* We can use **category** to declare some properties common for multiple trees. Example of that is *Social Entity*.

![Category][forest_category]

* Relation *submits* is common to both *Individual Test Subject* and *Group Test Subject* **role**s, so let's make more robust and DRY solution with **roleMixin** *Test Subject*.

![RoleMixin][forest_rolemixin]

* Now there is just one *submits* line - near and DRY. Can we do the same with *performs*? Obviously *Test Subject* and *AI Simulation* have again something in common but those don't have same rigidity. We must use **mixin** and because it is about ability to *perform* a *Test*, let's call it *Test Performer*.

![Mixin][forest_mixin]


[forest_kinds]: graphics/forest/01_kinds.png
[forest_sortals]: graphics/forest/02_sortals.png
[forest_relations]: graphics/forest/03_relations.png
[forest_category]: graphics/forest/04_category.png
[forest_rolemixin]: graphics/forest/05_rolemixin.png
[forest_mixin]: graphics/forest/06_mixin.png