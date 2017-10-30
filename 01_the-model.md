# The Model

First of all, let's take a look at our model which we are going to talk about.

![OntoUML model][model_plain]

Nice huh?! Now just a little reminder of basic OntoUML stereotypes (defined in UFO):

* **Kind** = rigid sortal providing identity
* **Subkind** = rigid sortal (not providing identity) - yeah, it is not in this model currently...
* **Role** = anti-rigid sortal which is relationally dependent
* **Phase** = anti-rigid sortal which depends just on intristic properties
* **Category** = rigid non-sortal
* **RoleMixin** = anti-rigid non-sortal which is relationally dependent (see the similarity with **Role**?)
* **Mixin** = semi-rigid non-sortal

If words like rigid or sortal are not clear to you, don't worry - we are going to find out!

Recall what you know about UML and notice which classes are abstract (hint: name is written by *italic*). All non-sortals are abstract classes and just like in programming, you cannot have instances of these and you must have some concrete subclasses to make instances. The inheritance is marked by lines with empty arrowhead. Now you have enough knowledge to know about identity...

## Mighty identity

Sortals are types which are not abstract, can be instantiated and for that they need the identity. Every object in the world needs to have one unique identity so you can tell if it is the same or if it is not. **Kind**s provide identity, each **kind** has a different principle of identity (it is a lot about philosophy and cognitive science - how we understand the world). Let me show you identity providers in the model.

![Identity providers in OntoUML model][model_idproviders]

Remember those colors showing different identity principles - those will be used in all materials here. So, **kind**s in this model provide the identity... but to who? To other sortals which are in their inheritance tree. Here is also important to say again that sortal must have exactly **one** identity and thus cannot inherit from multiple identity providers but just (and exactly) **one**!

![Identity in OntoUML model][model_identity]

As you can see identity spreads in opposite direction of inheritance and it means "no identity for non-sortals"...

## Disjoint/complete partitions

Last thing you remember from this short file is what **disjoint** and **complete** means:

* **disjoint** = there can not be object which is instance of multiple classes of this partition (e.g. *AI Simulation* object can be instance of exactly one of given phases: *Learning*, *Ready/Learned*, *Overlearned*. It means it cannot be *Learning* and *Ready/Learned* at the same moment.)
* **complete** = there can not be object which is not instance of some class of this partition (e.g. *AI Simulation* object must be instance of some of the given phases)

If you are still not sure about that, think about these classes (subclasses of *Integer*):

* class *A*: x < 0
* class *B*: x > 0
* class *C*: x < 2
* class *D*: x ≥ 0

Questions & answers (all regarding to *Integer* class):
* *Is partition to A and B disjoint?* - Yes! There is no number which is both in *A* and *B*.
* *Is partition to A and B complete?* - No! 0 does not belong to *A* nor *B*.
* *Is partition to B and C disjoint?* - No! Obviously 1 belongs to *B* as well as to *C*.
* *Is partition to B and C complete?* - Yes! There is no number which does not belong to *B* or *C*.
* *Is partition to A and C disjoint?* - No! There are many numbers which belong to both (e.g. -1).
* *Is partition to A and C complete?* - No! There are also some numbers which does not belong to *A* nor *C*.
* *Is partition to A and D disjoint?* - Yes! There is no number which would belong to *A* and *D*.
* *Is partition to A and D complete?* - Yes! Every number belongs to *A* or *D*.

(number is *Integer* instance in this case)

If you still don't get it, try to draw some Venn diagrams...

[model_plain]: graphics/model/01_model.png
[model_idproviders]: graphics/model/02_idproviders.png
[model_identity]: graphics/model/03_identity.png