# protocols

- HTTP is stateless, meaning every transaction on the internet is brand new and doesn't remember previous interactions unless context and metadata are explicitly provided.

- WebSockets provide bidirectional communication, reuse the connection, are persistent and stateful (can remember what happened previously), and are generally low latency because the connection stays open and doesn't require a handshake every time.

- Browsers don't support gRPC natively, requiring a library to interpret it. Additionally, it only works over HTTP/2 and uses protocol buffers which are not human-readable, making it better suited for service-to-service communication.

- GraphQL can fetch data from multiple sources (like news feeds, pictures, and ads) and make it look like one endpoint, whereas REST would require multiple separate calls to different endpoints.

- Server-Sent Events provide one-way communication from server to client, which is useful for scenarios like news feeds where you're just pushing events and don't care about client responses. WebSockets provide bidirectional communication where both client and server can send messages.

<hr />

## HTTP

- Key Characteristics
  ● simple
  ● human readable
  ● supported by all
  browsers
  ● stateless

- Common use cases

web browsers

## WebSockets

- Key Characteristics
  ● bi-directional communication
  ● persistent
  connection
  ● low-latency
  ● stateful

- Common use cases
  ● chat applications
  ● Live dashboards
  ● Collaborative editing

## Server-Sent Events

- Key Characteristics
  ● one-way
  communication
  (server to client)
  ● human readable

- Common use cases
  ● News feeds
  ● Status updates
  ● Stock tickers

## gRPC

- Key Characteristics
  ●binary protocol
  (HTTP/2)
  ● Strongly-typed
  contracts (proto
  buffs)
  ● requires code
  generation

- Common use cases
  ● Microservice
  communication
  ● Performance
  critical systems
  ● IoT devices

## REST

- Key Characteristics
  ● multiple endpointss
  ● human readable
  ● supported by all
  browsers
  ● stateless

- Common use cases
  ● single-sources of
  data
  ● CRUD apps
  ● easily cached data

## GraphQL

- Key Characteristics
  ● single endpoint
  ● precise data
  retrieval
  ● self-documenting
  API
  ● strongly typed

- Common use cases
  ● complex or multiple
  sources of data
  (Facebook
  homepage)
  ● apps supportingb
  multiple client types
  ● decoupling
  frontend from
  backend
  development