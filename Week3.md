Week 3:

-   Version Control

    -   Storage for;

        -   Source code

        -   Configuration files

        -   Assets (images, 3d models, \...)

        -   NOT binaries/ compiled files

    -   Tracking changes to files over time

-   Types of version control:

    -   Two major classifications:

        -   Centralized

        -   Distributed

    -   Centralized version control

        -   All developer pushed and changes made in subversion server
            and get back the latest one

        -   File stores centrally

        -   Changes are tracked

        -   Branching is easy

        -   Merging is hard

        -   Can't submit work offline

    -   Distributed version control

        -   Concepts and terminology are mostly the same

        -   Everybody gets a copy of the repository

        -   Branching and merging are easier

-   Branching strategies:

    -   Git flow

    -   GitHub flow

    -   Cactus

-   Testing

    -   Not to find bugs, help prevent introducing bugs with changes

    -   Show that your product works, ideally before deployment

    -   Goals:

        -   Verification: does it work?

        -   Validation: does it do what it needs to?

-   Unit testing

    -   Does a unit of code work by itself? (unit; method or whole
        class)

    -   Tested in **total isolation**

-   Integration testing: how things work together

    -   How these work together? Use real component that work together

    -   Testing across layers (e.g. make sure our logic layer can work
        with data layer,..)

-   System testing: does the whole thing work?

    -   Use real dependencies

-   Type of unit testing: white box vs black box

    -   Black box testing:

        -   Test behavior

        -   No concept how how the code is implemented, just what is
            should do

    -   White box testing;

        -   Test to the implementation

        -   Testing the code path

            -   Cover both branches of an if statement

-   Test must be:

    -   Deterministic

    -   Isolated

-   Writing Junit tests

    -   Use assert to verify stuffs

    -   Always include a message

        -   Helpful for self-documenting test

        -   Better understanding errors

-   Methods run before/after each tests:

    -   \@Before for creating instance class to test

    -   \@After for releasing any acquired resources

    -   Support test independence

-   Writing tests

    -   Test should be minimal

    -   One test method should test one thing

    -   Each implementation method may have many test methods

    -   Complicated tests imply complicated code
