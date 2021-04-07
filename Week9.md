Week 9:

-   **Flaky Test**: Test that used to always work, start "sometimes"
    working. If left unmitigated it can very quickly snowball and
    paralyzed an entire test suite.

-   Interesting patterns leading to flaky test:

    -   Hard code IDs: Postgres often uses sequences to decide on the id
        new records will get. They start at one and keep increasing.
        Most test frameworks like to roll back a database transaction
        after test runs, however the roll back does not roll back
        sequences.

    -   Random Data:

    -   Making bad assumption about DB ordering: incorrectly assumes
        that if you select the first row from the example below you are
        guaranteed to get 1.

> Create table test (a int)
>
> Insert test values (1)
>
> Insert test values (2)

-   The output of the SQL "select a from test limit 1" can be 1 or 2
    depending on factors. If one would like guaranteed ordering then
    use:

> Select a from test order by a limit 1

-   Incorrect assumption about time: "Test suite is not flaky unless
    it's from 11AM TILL 1PM"

-   Leaky global state:

-   Bad assumption about environment:

-   Concurrency:

-   Resource leaks:

```{=html}
<!-- -->
```
-   **Test Pyramid:** a way of thinking about how different kinds of
    automated tests should be used to create a balanced portfolio. It's
    essential point that you should have many more low-level UnitTest
    than high level BroadStackTests running through a GUI.

    -   Test through UI is slow, increasing build times, can only run on
        specific machines.

    -   Such tests are brittle, an enhancement to the system can break
        lots of such tests, even with good practices on writing them
        end-to-end tests are more prone to non-determinism problems,
        which undermine trust in them

        -   These tests are brittle, expensive to write, time consuming
            to run.

    -   Pyramid argues that you should do much more automated testing
        through unit tests than you should through traditional GUI based
        testing.

-   **End-to-End tests**:

    -   Developers like it because it offloads most of the testing to
        others.

    -   Manages and decision-makers like it because test that simulate
        real user scenarios can help them easily determine how failing
        test would impact the user.

    -   Testers like it because they often worry about missing a bug or
        writing a test that does not verify real-world behavior; writing
        tests from the user's perspective often avoids both problems.

-   **Unit test vs End-to-End test:**

    -   With end-to-End test, you have to wait: first for the entire
        product to be built, then for it to be deployed, and finally
        End-to-End tests to run. When the tests do run, flaky tests tend
        to be a fact of life. And even if a test finds a bug, that bug
        could be anywhere in the product.

    -   Although End-to-End tests do a better job of simulating real
        user scenarios, it's outweighed by all of disadvantages of end
        to end feedback loop.

> ![/var/folders/36/s2n9rjxs7yqd67gfytffhp0h0000gp/T/TemporaryItems/NSIRD_screencaptureui_U6CT85/Screen
> Shot 2021-04-06 at 3.29.22
> PM.png](media/image1.png){width="2.3887554680664915in"
> height="4.252777777777778in"}

-   **Integration tests:** Unit test has one major disadvantages: even
    if the units work well in isolation, you do not know if they work
    well together. But you don't need end-to-end test to do this.

    -   Integration test takes as small group of units, and tests their
        behavior as a whole, verifying that they coherently work
        together.

    -   If w units do not integrate properly, why write an end-to-end
        test when you can write a much smaller focused integration test
        that will detect the bug?

-   **Unit tests**: low level, close to the source of your application.
    Testing individual methods and functions of the classes, components
    or modules using by the software. Cheap to automate and can be run
    very quickly.

-   **Functional tests:** Focus on business requirements of an
    application. They only verify the output of an action and do not
    check the intermediate states of the system when performing that
    action.

-   **Functional tests vs.** **Integration tests:** an integration test
    may simply verify that you can query the database while a functional
    test would expect to get a specific value from the database as
    defined by the product requirement.

-   **Acceptance testing:** formal tests executed to verify if a system
    satisfies its business's requirements. Require the entire
    application to be up and running and focus on replicating user
    behaviors. Can also go further and measure the performance of the
    system and reject changes if certain goals are not met.

    -   Purely a functional testing to check the system behavior using
        the real data.

    -   Performed by end users to check if the system is built to match
        the business requirements of the organization.

    -   2 levels of testing:

        -   Alpha testing: called as off-site testing. During this
            testing, the testing team will verify the application in the
            presence of the end users

        -   Beta testing: should be done by the end users in their own
            environment in the presence of releasing team

    -   The defects found in acceptance testing are taken as failure
        product.

-   **Performance testing:** check the behaviors of the system when its
    under significant load. These test are non-functional and can have
    the various form to understand the reliability, stability, and
    availability of the platform. It can be observing response times
    when executing a high number of requests, or seeing how the system
    behaves with a significant of data. Costly to implements and run,
    can help to understand if new changes are going to degrade your
    system.

-   **Smoke testing:** check basic functionality of the application.
    Mean to be quick to execute, goal: give you the assurance that the
    major features of your system are working as expected.

-   **System testing:** end-to-end testing, is done on complete
    application software to check overall compliance of the product with
    the functional requirements.

    -   Tests written by users from user stories. This is a test that
        demonstrates that this type of user can do that thing.

    -   System testing is a type of application testing where we do not
        have any real interfaces. The system testing comes under black
        box testing.

    -   It is performed with demo data, not production data.

    -   Can be of functional testing and non-functional testing,
        performance load and stress test

    -   The defects found in system testing can be fixed based on
        priorities.
