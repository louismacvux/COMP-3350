Week 4: Test Driven Development

-   Write tests before implementation

-   Process:

    -   Write interface and method signatures

    -   Write one simple test, that fails

    -   Write just enough code to pass the test

    -   Clean up/improve the code (refractor)

-   Ensure complete test coverage (white box)

-   These are unit tests -- but test the interface

-   Technical debt:

    -   Implementing a feature, two ways to do it

        -   The quick but messy way

            -   Faster delivery

            -   Harder to make changes going forward (refractor, make
                previous code fails, ...)

        -   The slower but cleaner way

            -   Slower delivery

            -   Easier to make changes going forward

-   Technical debt quadrants:

+-------------+---------------------+------------------------------------+
|             | Reckless (bất cẩn)  | Prudent (khôn ngoan)               |
+=============+=====================+====================================+
| Deliberate  | Choose to move fast | Ship it choice                     |
| (Cố ý)      |                     |                                    |
|             | Code like hell      | Best way to go as fast as possible |
+-------------+---------------------+------------------------------------+
| Inadvertent | Most of assignment  | We learn something                 |
| (Vô tình)   |                     |                                    |
+-------------+---------------------+------------------------------------+
