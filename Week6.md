Week 6: Alternative pattern to inheritance

-   Inheritance modes "is a" relationship

-   We want to model behaviors

    -   Language independent: Composition, Aggregation, and delegation

-   Idea: extract and model behavior from an object

    -   Delegate responsibility of implementing behavior

-   Composition: Add behavior to a class by delegating responsibility of
    implementing that behavior to another class.

-   Aggregation: Add behavior to a class by delegating responsibility of
    implementing that behavior to another class.

-   Composition implies ownership of instance variables. When owing
    object is destroyed, embedded object is also destroyed

-   Aggregation does not imply ownership of instance variables. When
    object is destroyed, embedded object is not destroyed

-   Mixins:

    -   A class with methods that can be injected into other classes

    -   Get the behavior of a parent class without the "is a"
        relationship
