# 1.9.4

 - [#95](https://github.com/pardahlman/RawRabbit/issues/95) - Upgrade to .NET Core 1.0

Commits: b051f0938d...794dc48506


# 1.9.3

 - [#90](https://github.com/pardahlman/RawRabbit/issues/90) - Default Error Strategy tries to Ack Message twice +fix

Commits: e92022aa6f...186e67157b


# 1.9.2

.NET Core came a step closer to completion With the [announcement of the release of RC2](https://blogs.msdn.microsoft.com/webdev/2016/05/16/announcing-asp-net-core-rc2/). The new releases of Logging, Dependecy Injection and Configuration had a few breaking changes was handled. `RawRabbit` is now fully migrated to the new project structure. There are [new sample projects](https://github.com/pardahlman/RawRabbit/tree/master/sample) that combines .NET Core with RawRabbit (including Attributed Routing, Message Sequence etc.) and Serilog.

The underlying dependecy `RabbitMQ.Client` was updated, as it  [ 3.6.2 was released earlier this week](https://groups.google.com/forum/#!topic/rabbitmq-users/KCtezCXs1l8). While at it, all other NuGet dependencies was updated to its latest version.


 - [#89](https://github.com/pardahlman/RawRabbit/issues/89) - Add vNext Samples
 - [#88](https://github.com/pardahlman/RawRabbit/issues/88) - Upgrade to RabbitMQ.Client 3.6.2
 - [#87](https://github.com/pardahlman/RawRabbit/issues/87) - Implement Timeout for Sequences
 - [#86](https://github.com/pardahlman/RawRabbit/issues/86) - Use dedicated channel for publishing to error exchange
 - [#85](https://github.com/pardahlman/RawRabbit/issues/85) - Upgrade to .NET Core RC2
 - [#83](https://github.com/pardahlman/RawRabbit/issues/83) - Issue when QueueFullName matches an Exchange Name. contributed by ([johnbaker](https://github.com/johnbaker))
 - [#82](https://github.com/pardahlman/RawRabbit/issues/82) - Does RawRabbit runs on DNX Core 5.0 (.Net Core) ?
 - [#81](https://github.com/pardahlman/RawRabbit/issues/81) - Attributes for Routing/Queue/Exchange

Commits: b68cf973fa...e92022aa6f


# 1.9.1

 - [#80](https://github.com/pardahlman/RawRabbit/issues/80) - Use same JsonSerializer throughout the client
 - [#79](https://github.com/pardahlman/RawRabbit/issues/79) - Improve error handling

Commits: 5188354f20...a497734611


# 1.9.0

In this minor release, a breaking change in topology features in introduced, namely the default type for exchanges is `Topic` rather than `Direct`. Read through the [client upgrade](http://rawrabbit.readthedocs.org/en/master/client-upgrade.html) page for more information.

Thanks to [videege](https://github.com/videege), there is now a package for Ninject. We've also added logging adapters for the major logging frameworks (Serilog, NLog and log4net).

 - [#77](https://github.com/pardahlman/RawRabbit/issues/77) - Add logger packages
 - [#76](https://github.com/pardahlman/RawRabbit/issues/76) - Omit slash if virtual host is anything other than default
 - [#75](https://github.com/pardahlman/RawRabbit/issues/75) - Add extension for re-defining topology featuers
 - [#74](https://github.com/pardahlman/RawRabbit/issues/74) - Update MessageSequence Extension
 - [#73](https://github.com/pardahlman/RawRabbit/issues/73) - Append GlobalMessageId to routingkey
 - [#70](https://github.com/pardahlman/RawRabbit/pull/70) - RawRabbit.DependencyInjection.Ninject extension contributed by ([videege](https://github.com/videege))
 - [#69](https://github.com/pardahlman/RawRabbit/issues/69) - Add method to gracefully shut down client
 - [#35](https://github.com/pardahlman/RawRabbit/issues/35) - Return "subscription informaiton" on Subscribe/Respond

Commits: 0207aa75f2...2dc733c28e


# 1.8.13

 - [#72](https://github.com/pardahlman/RawRabbit/issues/72) - Add package for Ninject, contributed by Joshua Barron ([Originalutter](https://github.com/videege))
 - [#71](https://github.com/pardahlman/RawRabbit/issues/71) - Remove QueueingBasicConsumer
 - [#68](https://github.com/pardahlman/RawRabbit/issues/68) - Backward compatible Message Serialization
 - [#65](https://github.com/pardahlman/RawRabbit/issues/65) - Message Type serialization without assembly version, contributed by Marcus Utter ([Originalutter](https://github.com/Originalutter))
 - [#19](https://github.com/pardahlman/RawRabbit/issues/19) - Extension method for message sequences +feature

Commits: b928f96fc8...e1b84ef2f0


# 1.8.12

In this release, the `ChannelFactory` has been rewritten from the ground up. The old channel factory is left intact, but called `ThreadBasedChannelFactory`. One of the sync methods in the `IChannelFactory` interface is removed. It is recommended to use the async methods. All operations now use the new `ITopologyProvider` for creating topology features.

 - [#66](https://github.com/pardahlman/RawRabbit/issues/66) - Upgrade to RabbitMQ.Client 3.6.1
 - [#64](https://github.com/pardahlman/RawRabbit/issues/64) - Refactor Operations: Requester, Responder & Subscriber
 - [#59](https://github.com/pardahlman/RawRabbit/issues/59) - vNext & default ChannelFactory

Commits: bfa88b3083...3e7626fd0d


# 1.8.11

 - [#61](https://github.com/pardahlman/RawRabbit/issues/61) - Improve extraction of Application Name (contributed by ([Originalutter](https://github.com/Originalutter)))
 - [#41](https://github.com/pardahlman/RawRabbit/issues/41) - Correct order of arguments passed to Assert.Equal (contributed by ([Originalutter](https://github.com/Originalutter)))

Commits: e9a1693a0e...8cef898373


# 1.8.10

Improving invokation of Response handler.

 - [#60](https://github.com/pardahlman/RawRabbit/issues/60) - Improve handling multiple RPC Requests

Commits: 444efffedb...e4c3178885


# 1.8.9

Fixes a problem with subscriptions being terminated that was introduced in `1.8.8`.

 - [#58](https://github.com/pardahlman/RawRabbit/issues/58) - Subscribers are terminated +fix

Commits: 8b627ae192...c6f928addf


# 1.8.8

The first step in a refactoring has been taken. The aim is to increase thoughput by using async methods and allowing for multiple threads to publish messages.

Also, a new NuGet package, [`RawRabbit.DependencyInjection.Autofac`](https://www.nuget.org/packages/RawRabbit.DependencyInjection.Autofac) has been created.

 - [#57](https://github.com/pardahlman/RawRabbit/issues/57) - Refactor Operations: Publisher
 - [#55](https://github.com/pardahlman/RawRabbit/issues/55) - Support Autofac

Commits: 8b627ae192...13b86c7bf6


# 1.8.7

In this release the `ConnectionStringParser` has been polished by [Originalutter](https://github.com/Originalutter). It now supports all configuration parameters available in the configuration object. There are also some nice default values, like port `5672` which can be omitted from connection string.

An `KeyNotFound` issue  that sometimes occurred when performing multiple request synchronous (with `await`) was fixed.

 - [#53](https://github.com/pardahlman/RawRabbit/issues/53) - Avoid opening channels on Respond
 - [#50](https://github.com/pardahlman/RawRabbit/issues/50) - Unexpected connection close when multiple RPC
 - [#47](https://github.com/pardahlman/RawRabbit/issues/47) - Add default attributes
 - [#44](https://github.com/pardahlman/RawRabbit/issues/44) - Update QueueArgument with LazyQueue
 - [#42](https://github.com/pardahlman/RawRabbit/issues/42) - Allow connection strings without parameters
 - [#25](https://github.com/pardahlman/RawRabbit/issues/25) - Support more parameters to connectionString

Commits: f0d5128726...09aaea56be
