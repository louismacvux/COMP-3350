Week 7:

-   Design pattern: typical solutions to commonly occurring problems in
    software design.

    -   Is not a specific piece of code but a general concept for
        solving particular problems.

    -   Are often confused with algorithm. However, algorithm defines a
        clear set of actions, while pattern is a more high-level
        description of a solution.

-   Classification of patterns:

    -   Creational patterns: object creation mechanisms that increase
        flexibility and reuse of existing code.

    -   Structural patterns: explain how to assemble objects and classes
        into large structures, while keeping the structures flexible and
        efficient.

    -   Behavioral patterns: take care of effective communication and
        the assignment of responsibilities between objects.

-   **Patterns:**

    -   **Builder:** creational pattern, let's you construct complex
        objects step by step. Allows you to produce different types and
        representations of an object using the same construction code.

        -   Extract the object construction code out of its own class
            and move it to separate objects called **builders**.

        -   To create an object, you execute a series of builders that
            are necessary for a particular object.

        -   With different object, the same builder can be implemented
            differently. Can create several builders in different
            manner.

        -   **Director:** A preset of builders for a typical kind of
            object. Not necessary as you can call each builder
            separately, but if some kinds of object need similar set of
            builders, these builders can be put in a director.

        -   **Application:**

            -   When you want your code to be able to create different
                representations of some product (wooden and concrete
                house)

            -   To construct composite trees or other complex objects.
                Builder doesn't expose the unfinished product while
                running construction steps. Prevents the client code
                from fetching unfinished products.

        -   **Pros:**

            -   Construct object step-by-step, defer construction steps
                or run steps recursively.

            -   Reuse the same construction code when building various
                representations of products

            -   Isolate complex construction code form the business
                logic of the product.

        -   **Cons:**

            -   Overall complexity of the code increase since the
                pattern requires creating multiple new classes.

    -   **Singleton:** creational pattern, let's you ensure that a class
        has only one instance, when providing a global access point to
        this instance.

        -   Make the default constructor private, to prevent other
            objects from, using the new operator with singleton class.

        -   Create static creation method that acts as a constructor.
            This method calls the private constructor to create an
            object and saves it in a static field. All following calls
            to this method return the created object.

        -   **Application:**

            -   When a class should have just a single instance
                available to all clients (single database object shared
                by different parts of the program)

            -   When you need stricter control over global variables.

        -   **Pros:**

            -   Can be sure that a class has only a single inheritance.

            -   Gain a global access point to that instance

            -   Singleton object is initialized only when it's requested
                for the first time.

        -   **Cons:**

            -   Can mask bad design, when the components know too much
                about each other.

            -   Require special treatment in a multithreaded environment
                so that multiple threads won't create a single ton
                object several times.

            -   Difficult to write unit test the client code.

    -   **Factory Method**: creational pattern, provides an interface
        for creating objects in a superclass, but allow subclass to
        alter the type of objects that will be created.

        -   Replace direct object construction calls with calls to a
            special factory method.

        -   **Application:**

            -   When you don't know beforehand the exact types and
                dependencies of the objects your code should work with

            -   When you want to provide users of your library or
                framework with a way to extend its internal components.

            -   When you want to save system resources by reusing
                existing objects instead of rebuilding them each time.

        -   **Pros:**

            -   Avoid tight coupling between the creator and the
                concreate products

            -   Single Responsibility Principle. You can move the
                product creator conde into one place in the program,
                making the code easier to support.

            -   Open/Close principle. Introduce new types of products
                into the program without breaking the existing client
                code.

        -   **Cons:**

            -   Code may become more complicate since you introduce a
                lot of new subclasses to implement the pattern.

    -   **Adapter:** structural pattern, allows object with incompatible
        interfaces to collaborate

        -   Create an adapter -- an object that converts the interface
            of one object so that another object can understand it.

        -   Not only can convert data into various formats but can also
            help objects with different interfaces collaborate.

            -   Adapter gets an interface, compatible with one of the
                existing objects.

            -   Using this reference, existing object can safely call
                the adapter's objects.

            -   Upon receiving a call, the adapter passes the request to
                the second object, but in a format and order that the
                second object expects.

        -   **Application:**

            -   When you want to use some existing class, but its
                interface isn't compatible with the rest of your code.

            -   When you want to reuse several existing subclasses that
                lack some common functionality that can't be added to
                the superclass.

        -   **Pros:**

            -   Single Responsibility Principle. Separate the interface
                or data conversion code from the primary business logic
                of the program

            -   Open/Close Principle. Introduce new types of adapters
                into the program without breaking the existing code, as
                long as they work with the adapters through the client
                interface.

        -   **Cons:**

            -   Overall complexity of the code increase because you need
                to introduce a set of new interfaces and classes.

            -   It's simpler just to change the service class so that it
                matches the rest of your code.

    -   **Facade:** structural pattern, provides a simplified interface
        to a library, a framework, or any other complex set of classes.

        -   A class that provides a simple interface to a complex
            subsystem which contains lots of moving parts.

        -   Might provide limited functionality in comparison to working
            with the subsystem directly, but still includes only those
            features that are cared about.

        -   E.g. Write a video converter class so that using the video
            conversion library more simple

        -   **Application:**

            -   When you need to have a limited but straightforward
                interface to a complex subsystem

            -   When you want to structure a subsystem into layers

        -   **Pros:** can isolate your code from the complexity of a
            subsystem

        -   **Cons:** can become a god object coupled to all classes of
            an app

    -   **Special case:**

        -   If it's possible for a variable to be null, you have to
            remember to surround it with null test code so you'll do the
            right thing if null is present.

        -   Instead of returning null, or some odd value, return a
            Special Case that has the same interface as what the caller
            expects.

    -   **Chain of Responsibility:** behavioral pattern, lets you pass
        requests along a chain of handlers. Upon receiving a request,
        each handler decides either to process the request or to pass it
        to the next handler.

        -   Transforming particular behaviors into stand-alone objects
            called handler.

        -   Link these handlers into a chain. Each linked handler has a
            field to store a reference to the next handler in the chain.
            In addition to processing a request, handlers pass the
            request further along the chain. Request travels along the
            chain until all handlers have a chance to process it.

        -   **Application:**

            -   When your program is expected to process different kinds
                of requests in various ways, but exact types of requests
                and their sequences are unknown beforehand.

            -   When it's essential to execute several handlers in a
                particular order.

            -   When the set of handlers and their order are supposed to
                change at runtime.

        -   **Pros:**

            -   Control the order

            -   Single Responsibility Principle

            -   Open/Close Principle

        -   **Cons:** Some requests may end up unhandled

    -   **Observer:** behavioral pattern, lets you define a subscription
        mechanism to notify multiple objects about any events that
        happen to the object they're observing,

        -   The object that notify other objects about the changes to
            its state is called publisher. All other objects that want
            to track changes to publisher are called subscriber.

        -   This mechanism consists of: (1)an array field for storing a
            list of references to subscribe objects and (2) several
            public methods which allow adding subscriber to and removing
            them from that list.

        -   **Applications:**

            -   When changes to the state of one object may require
                changing other objects and the actual set of objects is
                unknown beforehand or change dynamically.

            -   When some objects in your app must observe others, but
                only for a limited time or in specific cases.

        -   **Pros:**

            -   Open/Close principle.

            -   Can establish relations between objects at runtime.

        -   **Cons**: subscriber are notified in random order.

    -   **Dependency Injection:** giving an object its instance
        variable.

        -   We could pass the variable into the constructor. That would
            "inject" the "dependency" into the class. Now we use the
            variable (dependency), we use the object that we were given
            rather than the one we created.

    -   **Iterator:** behavioral pattern, lets you traverse elements of
        a collection without exposing its underlying representation.

        -   Extract the traversal behavior of a collection into a
            separate object called an iterator.

        -   An iterator object encapsulates all of the traversal
            details, such as the current position and how many elements
            are left till the end.

        -   Several iterators can go through the same collection at the
            same time, independently.

        -   **Applicability:**

            -   When your collection has a complex data structure under
                the hood, but you want to hide its complexity from
                clients

            -   To reduce duplication of the traversal code across your
                app

            -   When you want your code to be able to traverse different
                data structure or when types fo these structure are
                unknown beforehand.

        -   **Pros:**

            -   Single Responsibility Principle

            -   Open/Close Principle

            -   Can iterate over the same collection in parallel because
                each iterator object contains its own iteration state.

            -   You can delay an iteration and continue when needed.

        -   **Cons:**

            -   Applying the pattern can be an overkill if your app only
                works with simple collections.

            -   Maybe less efficient than going through elements of some
                specialized collection directly.

        -   
