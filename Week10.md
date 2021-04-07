Week 10:

-   Problem with Legacy Software

    -   It's impossible to perform refactoring without breaking the
        working code.

    -   Legacy applications are often critical to the business and have
        been used for many years, since the business is always changing,
        there is constant pressure to support additional requirements
        and fix existing bugs.

    -   Reasons:

        -   Original developers are gone, no one understands how the
            application is implemented.

        -   Technologies used in the application are no longer current,
            having been replaced

    -   Renovation of legacy systems involves considerable
        re-architecting.

-   Understand Legacy Software:

    -   How it is used: critical to understand the design.

    -   How it is deployed:

    -   How it is built: This is true for languages like C/C++ where
        there are a variety of compile time options when generating
        object files.

    -   How it is Structured: This is an area that developers care about
        a lot and large part of complexity resides.

-   What can do:

    -   Examining the existing artifacts. File/Directory structure or
        package/namespace structure

    -   Apply partitioning and clustering algorithms to discover the
        layers and independent component.

    -   Experiment with what-if architecture.

    -   Ask the dev and architects who have been supporting the
        application.

-   Seams: the connection between existing code and your new code. Where
    is the existing code going to call the new code? We need to make
    this seam, then test it.

    -   Break existing code up into testable units.

    -   Insert a seam where your code will go

    -   Write unit tests for existing code

    -   Existing behavior is correct behavior.
