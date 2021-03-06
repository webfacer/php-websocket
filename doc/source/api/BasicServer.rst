-------------------
Wrench\\BasicServer
-------------------

.. php:namespace: Wrench

.. php:class:: BasicServer

    .. php:const:: EVENT_SOCKET_CONNECT

        Events

    .. php:attr:: rateLimiter

    .. php:attr:: originPolicy

    .. php:attr:: uri

        The URI of the server

    .. php:attr:: options

        Options

    .. php:attr:: logger

        A logging callback

        The default callback simply prints to stdout. You can pass your own logger
        in the options array. It should take a string message and string priority
        as parameters.

    .. php:attr:: listeners

        Event listeners

        Add listeners using the addListener() method.

    .. php:attr:: connectionManager

        Connection manager

    .. php:attr:: applications

        Applications

    .. php:attr:: protocol

    .. php:method:: __construct(string $uri, array $options = Array)

        Constructor

        :param string $uri:
        :param array $options:

    .. php:method:: configure($options)

        :param unknown $options:

    .. php:method:: configureRateLimiter()

    .. php:method:: configureOriginPolicy()

        Configures the origin policy

    .. php:method:: addAllowedOrigin(array $origin)

        Adds an allowed origin

        :param array $origin:

    .. php:method:: configureLogger()

        Configures the logger

        :returns: void

    .. php:method:: configureConnectionManager()

        Configures the connection manager

        :returns: void

    .. php:method:: getConnectionManager()

        Gets the connection manager

        :returns: \Wrench\ConnectionManager

    .. php:method:: getUri()

        :returns: string

    .. php:method:: setLogger(Closure $logger)

        Sets a logger

        :param Closure $logger:
        :returns: void

    .. php:method:: run()

        Main server loop

        :returns: void This method does not return!

    .. php:method:: log(string $message, $priority = info)

        Logs a message to the server log

        The default logger simply prints the message to stdout. You can provide a
        logging closure. This is useful, for instance, if you've daemonized and
        closed STDOUT.

        :param string $message: Message to display.
        :param unknown $priority:
        :returns: void

    .. php:method:: notify(string $event, array $arguments = Array)

        Notifies listeners of an event

        :param string $event:
        :param array $arguments: Event arguments
        :returns: void

    .. php:method:: addListener(string $event, Closure $callback)

        Adds a listener

        Provide an event (see the Server::EVENT_* constants) and a callback
        closure. Some arguments may be provided to your callback, such as the
        connection the caused the event.

        :param string $event:
        :param Closure $callback:
        :returns: void

    .. php:method:: getApplication(string $key)

        Returns a server application.

        :param string $key: Name of application.
        :returns: Application The application object.

    .. php:method:: registerApplication(string $key, object $application)

        Adds a new application object to the application storage.

        :param string $key: Name of application.
        :param object $application: The application object
        :returns: void

    .. php:method:: configureProtocol()

        Configures the protocol option
