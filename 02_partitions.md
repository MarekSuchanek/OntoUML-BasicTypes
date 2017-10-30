# Partitions

Now we take [our simple model](01_the-model.md) and try to explain it with pictures of partitions we see in our modeled world. If you want, you can draw it on a paper to get into it...

* First, let's draw a rectangle... All objects in our modeled world belong into the rectangle and what is outside does not matter to us. We will represent objects as simple dots.

![Our world with objects][partitions_world]

* As you know in OntoUML we use types/classes to classify (notice: class - to classify) our objects. Let start with our **kind**s (literaly kinds of objects). We have exactly five in our model and kinds are by their definition always disjoint (we don't want objects with more identities, right?!).

![Kinds][partitions_kinds]

* We used some colors in our model to show different principles of identity... Let's do it here as well and it won't be so boring hopefully.

![Identity (colors)][partitions_identity]

* Objects are now hidden and before adding them back we will add *anti-rigid sortals* (**role**s and **phase**s). *Rigid* is something what "does not change" (in all situations remains object remains in the class) and logically *anti-rigid* is something what "can change" (in some situation it is not in the class but in some it is).

   We will capture that using different style of lines... If you are driver or at least know basics of driving, then it will be very natural for you. Solid line means "do not cross" - objects can not cross it in any direction (in/out) and broken/dashed line allows such crossing.

   Firstly we have 3 **phase**s in *AI Simulation* **kind** (notice that it is disjoint and complete partition) depicted with blue color. Then we have **role**s for **kind** *Person* - *Supervisor* (orange color) and *Individual Test Subject* (red color), as you can see person can have one of those roles, none or both at the same time. And finally *Group Test Subject* **role** of *Group* by green color.

![Anti-rigid sortals][partitions_sortals]

* Back to our objects... Object can "move" within solid partition to which they belong.

   Imagine that you are a dot in *Person* partition (draw it if you need with different color). You might be an *Individual Test Subject*, *Supervisor*, both or none of those and this can change over your lifespan (until your dot is there) = *anti-rigid*. But you can not escape from being a *Person* (being a dot in green partition) = *rigid*.

![Instances 1][partitions_instances1]

![Instances 2][partitions_instances2]

* **Category** *Social Entity* have some properties which are common for both *Group* and *Person* **kind**s. We can draw this in our partitions as solid line (light blue) enclosing both those kinds. Again, solid means *rigid* and we see that there are two principles of identity "inside" - that indicates *non-sortal* (abstract class, based on common properties, different identity principles).

![Category][partitions_category]

* Again shortly back to objects and specifically **role**s. In the first following picture you can identify some object "in" roles. But roles have relational dependency (**role** needs to be connected to something, it is mandatory)... For now let's draw relations for *Group Test Subject*s and *Individual Test Subject*s (we skip now relation for *Supervisor* role for the sake of clarity).

![Roles][partitions_roles1]

![Roles with relations][partitions_roles2]

* We see that this dependency is common for both **role**s from different **kind**s. That indicates right place to use **roleMixin**! It is *anti-rigid* (broken/dashed line) and *non-sortal* (spreads across multiple identities). In the picture it is by pink color. Objects still can go in/out roles but can not cross solid line separating **kind**s.

![RoleMixin][partitions_rolemixin]

* So that was about the relation *submits* (for being *Test Subject* you must *submit* a *Tester's Application*). In next picture you can see the *performs* relation (*Test Subject* or *AI Simulation* *performs* a *Test*). It is there exactly 3 times...

![Relation performs][partitions_performs]

* But that indicates that *Test Subject* and *AI Simulation* have something in common!

   Can we enclose them in **Category**? No! That would restrict objects "leaving" **role**s. We want to allow people to quit to be an *Individual Test Subject*s one day and others to become an *Individual Test Subject*...

   How about **roleMixin**? No! *AI Simulation* is a **kind**, not a **role**.

   It must be **mixin** then! It is *semi-rigid* *non-sortal* and we can see it in the picture below as dark pink line which is solid around *AI Simulation* and broken/dashed around *Test Subject*.

![Mixin][partitions_mixin]

* To be complete we can finally add *supervises* relation (*Supervisor* *supervises* a *Test*) and we are done here!

![Relation supervises][partitions_supervises]

[partitions_world]: graphics/partitions/00_world_objects.png
[partitions_kinds]: graphics/partitions/01_partitions.png
[partitions_identity]: graphics/partitions/02_identity.png
[partitions_sortals]: graphics/partitions/03_antirigid_sortals.png
[partitions_instances1]: graphics/partitions/04_instances.png
[partitions_instances2]: graphics/partitions/05_instances.png
[partitions_category]: graphics/partitions/06_category.png
[partitions_roles1]: graphics/partitions/07_instances.png
[partitions_roles2]: graphics/partitions/08_relations1.png
[partitions_rolemixin]: graphics/partitions/09_rolemixin.png
[partitions_performs]: graphics/partitions/10_relation_performs.png
[partitions_mixin]: graphics/partitions/11_mixin.png
[partitions_supervises]: graphics/partitions/12_relation_supervises.png
