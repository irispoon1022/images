-   aws app sync
    -   traditional architecture
        -   !\[\](/img/uploads/a94314f070d34b528b89097b019264711608424623079image.png)
        -   
    -   questions
        -   The Amplify DataStore provides a queryable on-device
            DataStore for web, mobile and IoT developers with a
            local-first and familiar programming model to interact with
            data seamlessly whether you're online or offline. When
            combined with AWS AppSync the DataStore can leverage
            advanced versioning, conflict detection and resolution in
            the cloud allowing to automatically merge data from
            different clients as well as providing data consistency and
            integrity.
        -   Since AWS AppSync supports AWS Lambda, Amazon DynamoDB and
            Amazon Elasticsearch, the GraphQL operations can be simple
            lookups, complex queries & mappings, full text searches,
            fuzzy/keyword searches or geo lookups.
        -   what if i want to connect multiple api?
            -   it seems not ready yet
        -   what if i want to connect multiple databases?
            -   it seems not ready yet
    -   product
        -   pricing
            -   data query
            -   data modification
            -   volume of data transfer
            -   real time update
            -   cache
    -   developer guide
        -   
    -   https://aws.amazon.com/graphql/guide/
-   basic concepts
    -   why/ benefits
        -   \*\*Query\*\*
            -   request for the exact data you need without changing the
                API server
                -   REST is a set of structured endpoints according
                    clients\' data needs. With GraphQL, there\'s no need
                    to adjust API when product requirements changes from
                    the client side.
                    -   when working with REST API, data is loaded from
                        specific endpoints. each endpoint has a clearly
                        defined structure of the information that it
                        returns. this mean with REST, the data
                        requirement of a client are effectively encoded
                        in the URL that it connects to.
            -   reduce the number of network request
            -   query data from one or more data sources with a single
                network request using GraphQL
        -   seamless versioning
        -   Caching
            -   AWS AppSync's server-side data caching capabilities
                reduce the need to directly access data sources by
                making data available in high speed in-memory managed
                caches, delivering data at low latency. Being fully
                managed, it eliminates the operational overhead of
                managing cache clusters. By providing the flexibility to
                selectively cache data fields and operations defined in
                the GraphQL schema with customizable expiration, data
                caching further enables developers to configure optimal
                performance for their business needs.
        -   \*\*Real Time Push data\*\*
            -   AWS AppSync can push real-time data updates over
                Websockets to millions of clients - can be used in
                situations when users expects real time data like
                banking alerts, news updates chat applications or
                collaboration tools
            -   !\[\](/img/uploads/9aec67df84504607ab9d5a8e6846221b1608376363993image.png)
                -   AWS AppSync lets you specify which portions of your
                    data should be available in a real-time manner using
                    GraphQL Subscriptions.
        -   appolo client further simplify things?
    -   \^\^Client side\^\^
        -   different clients written in different languages all have
            their own sdk to talk to graphql?
        -   when does the customization happen? on the graphql client
            side or server side
            -   the customization happen at the client side
    -   \^\^Server side\^\^
        -   Why do we need a schema? What is a schema?
            -   the schema is to define the capabilities (available
                resources one can possibly query) of the API. It works
                as the contract between client and server. once the
                schema is defined, frontend and backend teams can work
                completely independent from each other
                -   Every GraphQL schema has three special \*\*root
                    types\*\*: Query, Mutation, and Subscription. The
                    root types correspond to the three operation types
                    offered by GraphQL: queries, mutations, and
                    subscriptions. The fields on these root types are
                    called \*\*root fields\*\* and define the available
                    API operations.
                    -   !\[\](/img/uploads/095204b04eab44849c65018e7772957e1608515651182image.png)
                    -   
                -   When the type of a root field is an object type, you
                    can further expand the query (or
                    mutation/subscription) with fields of that object
                    type. The expanded part is called selection set.
                -   !\[\](/img/uploads/c6f2cf1eb8ae43a0a76f8c737ce337f11608516014068image.png)
                -   !\[\](/img/uploads/ed66ab7fab2c429ea5a53d367b1e6e931608516292207image.png)
                -   source:
                    https://www.howtographql.com/graphql-js/1-getting-started/
                -   
        -   define the schema in ui and from a source file?
            -   maybe not very important
        -   How does graphql talk to different types of databases/apis?
            how does it resolve the entities defined in the schema with
            the one in databases?
            -   every field in the schema correspond to a resolver
                function in the graphQL server.
    -   https://www.howtographql.com/basics/2-core-concepts/
    -   GraphQL is only a specification. This means that GraphQL is in
        fact not more than a long document that describes in detail the
        behaviour of a GraphQL server. You have to build the GraphQL
        server yourselves.
    -   what is appolo?
        -   There are two major GraphQL clients available at the moment.
            The first one is Apollo Client, which is a community-driven
            effort to build a powerful and flexible GraphQL client for
            all major development platforms. The second one is called
            Relay and it is Facebook's homegrown GraphQL client that
            heavily optimizes for performance and is only available on
            the web. They free you up from these tasks:
            -   send queries and mutations directly without constructing
                HTTP requests
            -   view-layer integration
            -   caching
            -   validation and optimization of queries based on the
                schema
-   our product
    -   2 different value proposition (greenfield?)
        -   general graphql as a service
            -   api owner (who has a large number of various api
                consumers)
                -   frequent requests to change the api?
                -   complains about the API was not flexible enough?
                -   teams having vastly different requirements on what
                    subset of the data it needs to access?
                -   the problem of api owner is well articulated in this
                    article:
                    https://medium.com/walmartglobaltech/open-sourcing-lacinia-our-graphql-library-for-clojure-96a4ce5fc7b8
            -   api consumer
                -   frequent request to change the api?
                -   making multiple requests to assemble a complete view
                    of a resource?
                -   slowness?
            -   need to find collaborators and priortize integrations
                according to the actual use case
        -   cloud inventory?
            -   need to find collaborators and priortize integrations
                according to the actual use case
            -   gaia portal
    -   companies using graphql
        -   https://tyk.io/how-airbnb-shopify-github-and-more-are-winning-with-graphql-and-why-you-may-need-it-too/
        -   https://www.graphql.com/case-studies/
        -   
    -   converting REST to GraphQL automatically
        -   https://www.apollographql.com/blog/courseras-journey-to-graphql-a5ad3b77f39a/
    -   landscape
        -   https://landscape.graphql.org/zoom=200
        -   
