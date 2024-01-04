# RequestReplyJMS

Sample Request-Reply implementation using JMS to decouple components

## Summary

This sample system contains two architectural components:

- The Transaction Service, providing a REST API endpoint for clients to submit transactions (purchases)
- The Tax Service, which calculates the applicable tax for a given transaction

These two services need to be loosely coupled since tax rules change independendly (and often!).
The services communicate through a contract defined in the CommonModel project using Protobufs.

This approach uses JMS (specifically Apache ActiveMQ) and the QueueRequestor class to enable communication
 between the services in a request-reply model.
