Week 5:

-   Coupling: measuring dependencies between components (we want low
    coupling)

    -   Looking at what it communicates with

-   Cohesion: measuring relationships within a component (high cohesion
    = good)

    -   Looking at itself

-   Tools to manage coupling and cohesion

    -   DRY -- don't repeat yourself

        -   Code or behavior. Copy paste or repeat

        -   E.g. validation in two places

        -   Observe and resolve during factoring

        -   Helps reduce coupling

    -   LoA -- Levels of Abstraction

        -   Define an interface (what your unit can do without
            specifying how)

        -   Hide implementation details from the caller

        -   Helps reduce coupling

    -   SoC -- Separation of Concerns

        -   Application logic should not know about presentation
            (n-tier)

        -   Help increase cohesion and reduce coupling

    -   PoLK -- principle of Least Knowledge

        -   Each unit knows about itself and interfaces it depends on

        -   Help reduce coupling

    -   PoLA -- principe of Least Astonishment

        -   What do you expect this thing to do

        -   Answer should not differ from what actually happens

-   Refactoring: change implementation without changing behavior

    -   Goals: increase maintainability, readability, reduce code smells

-   Refactoring: there are many named refactorings:

    -   Simple data-level refactoring (renaming, named constants)

    -   Statement-level refactoring (decomposing complex Boolean
        expressions)

    -   Routine-level refactoring (decompose method, convert method to
        class)

    -   Class implementation refactoring (moving methods)

    -   Class interface refactoring (move methods, separate classes)

-   Five keys indicating smells: SOLID

    -   S: Single responsibility

    -   O: Open and close: if you have a class, and if you need to
        modify, you don't have to modify that class. Open for extension
        but close for changes. Can make subclass and change in that
        subclass

    -   L: Subtitution: inherit from interface, you should be able to
        use any subclass, shouldn't change meaning of what this class
        does.

    -   I: Interface: understandable, readable and tight

    -   D: Dependency inversion principle: depend on interface. You
        should go across layer or across class, not depend on a class,
        should depend on interface.

```{=html}
<!-- -->
```
-   Dependency injection: Use parameter to inject stuff we have options
    to choose from

    -   We can use any database

    -   Unit test can fake implementations, program can use real
        implementations

    -   Can be use everywhere

        -   Command line arguments

        -   Which config file to use

        -   Other patterns use this one
