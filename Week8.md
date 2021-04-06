Week 8:

-   Untested Code: Some piece of code in the SUT is not being exercised
    by any test, because we've never seen it execute

-   **Test Double:**

    -   How it works: Like double stunt in movies, we can replace the
        real depend-on component (DOC) with our equivalent of the "stunt
        double": Test Double.

        -   Depends on what kind of test we are executing we may
            hard-code the behavior of the Test Double or we may
            configure during set up phase.

        -   When the system under test (SUT) interacts with the Test
            Double, it won't be aware that it isn't talking to the real
            components.

        -   We don't need to implement the whole interface of DOC, we
            only provide whatever functionality is needed for our test.

    -   When to use it:

        -   If we have an Untested Requirement

        -   If we have Untested Code and DOC doesn't provide the control
            point to allow us to exercise the SUT with the necessary
            indirect inputs.

        -   If we have Slow Test and we want to be able to run our tests
            more quickly and more often.

-   **Variation: Test Stub:** use this to replace a real component on
    which the SUT depends so that the test has a control point for the
    indirect inputs of the SUT. This allows the test to force the SUT
    down paths it might not otherwise execute.

    -   We replace a real object with a test-specific object that feeds
        the desired indirect inputs into the SUT

    -   **How it works:** We define a test-specific implementation of an
        interface on which the SUT depends. It's configured to respond
        to calls from the SUT with the values that will exercise the
        Untested Code within the SUT.

        -   We install the Test Stub so that the SUT uses it instead of
            the real implementation. When called but the SUT during
            test, the Test Stub returns the previously defined values.

        -   The test can then verify the expected outcome in the normal
            way.

    -   **When to use:**

        -   When you have Untested Code caused by the inability to
            control the indirect inputs of the SUT. We can also use a
            Test Stub to inject values that allows us to get past a
            particular point in the software where it calls software
            that is unavailable in our test environment.

-   **Mock Object:** Replace the DOC of SUT with a test-specific object
    that verifies it is being used by the SUT.

    -   **How it works:** We define a Mock Object that implements the
        same interface as DOC. We configure the Mock Object with the
        values with which it should respond to the SUT and the method
        calls to expect from the SUT

        -   When called during the SUT execution, the Mock Object
            compares the actual arguments received with the expected
            arguments using Equality Assertions and fails if they don't
            match.

    -   **When to use:**

        -   Use as an observation point when we need to do Behavior
            Verification to avoid having an Untested Requirement caused
            by an inability to observe side-effect of invoking methods
            on the SUT.

        -   Need to be able to predict the value of most or all
            arguments of the method calls before we exercise the SUT.

        -   Often use the equals method of the various objects being
            compared.

        -   Mock object can be either "strict" or "lenient", depends on
            whether out of order calls is tolerable or not.

-   **Fake Object:** replace a component that SUT depends on with a much
    lighter-weight implementation.

    -   The interactions the SUT made with other components may be
        necessary but the side effect of these interactions may be
        unnecessary or detrimental.

    -   **How it works:** Build a very lightweight implementation of the
        same functionality as provided by DOC and instruct the SUT uses
        it instead of the real DOC. It need not have any of the ability
        that real DOC have. Only need to provide equivalent services to
        the SUT so that the SUT isn't aware it isn't using the real DOC.

        -   A kind of Test Double that is similar to Test Stub, but
            while Test Stub acts as a control point to inject indirect
            inputs in to SUT, the Fake Object does not, merely provides
            a way for the interactions to occur in a self-consistent
            manner.

    -   **When to use it:**

        -   Whenever our SUT depends on other components that are
            unavailable or which make testing difficult or slow.

        -   It must be easier to create a light-weight implementation
            than it would be to build and program suitable Mock Object
            to make Fake Object worthwhile.
