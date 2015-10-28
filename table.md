This document is the central organizational point for LoopBack examples, which are divided into the following broad categories:

- [Tutorials](#tutorials)
- [Topic-specific examples](#topic-specific-examples)
- [Connector examples](#connector-examples)
- [Client SDK examples](#client-sdk-examples)

## Tutorials

Each tutorial provides step-by-step instructions to create an example app that illustrates one or more
core LoopBack features.
In general, these tutorials are intended to be followed in order.

<table><thead>
<tr>
<th align="center">Order</th>
<th width="320">Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td align="center">1</td>
<td>
<a href="https://github.com/strongloop/loopback-getting-started">loopback-getting-started</a></td>
<td><b>START HERE</b> to learn the basics of LoopBack. Follow <a href="http://docs.strongloop.com/display/LB/Getting+started+with+LoopBack">Getting started with LoopBack</a> to understand it.</td>
</tr>
<tr>
<td align="center">2</td>
<td>
<a href="https://github.com/strongloop/loopback-getting-started-intermediate">loopback-getting-started-intermediate</a></td>
<td>Full-stack example that builds on <code>loopback-getting-started</code>. Follow <a href="http://docs.strongloop.com/display/LB/Getting+started+part+II">Getting started part II</a> to understand it.</td>
</tr>
<tr>
<td align="center">3</td>
<td>
<a href="https://github.com/strongloop/loopback-example-database">loopback-example-database</a></td>
<td>Basic database-related features.</td>
</tr>
<tr>
<td align="center">4</td>
<td>
<a href="https://github.com/strongloop/loopback-example-relations">loopback-example-relations</a></td>
<td>Model relations and filtering via REST</td>
</tr>
<tr>
<td align="center">5</td>
<td>
<a href="https://github.com/strongloop/loopback-example-app-logic">loopback-example-app-logic</a></td>
<td>How to add your own logic to a LoopBack app</td>
</tr>
<tr>
<td align="center">6</td>
<td>
<a href="https://github.com/strongloop/loopback-example-access-control">loopback-example-access-control</a></td>
<td>Controlling access to your API endpoints</td>
</tr>
</tbody></table>

## Topic-specific examples

The following examples may be completed in any order.

<table><thead>
<tr>
<th width="320">Name</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>
<a href="https://github.com/strongloop/angular-live-set-example">angular-live-set-example</a></td>
<td>LoopBack/AngularJS app using HTML5 server-sent events.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-component-push/tree/master/example/server-2.0">loopback-component-push</a></td>
<td>Example of using <a href="https://docs.strongloop.com/display/LB/Push+notifications">LoopBack Push Component</a>.
<br/>NOTE: Example is in the <code>example/serve-2.0</code> directory.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-component-storage/tree/master/example-2.0">loopback-component-storage</a></td>
<td>Example of using <a href="https://docs.strongloop.com/display/LB/Storage+component">LoopBack storage component</a>.
<br/>NOTE: Example is in the <code>example-2.0</code> directory.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-app">loopback-example-app</a></td>
<td>A full-stack LoopBack application (iCars).</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-mixins">loopback-example-mixins</a></td>
<td>Loading mixins, observing changes, and adding model attributes.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-pubsub">loopback-example-pubsub</a></td>
<td>Example using strong-pubsub.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-offline-sync">loopback-example-offline-sync</a></td>
<td>Offline sync with Loopback.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-passport">loopback-example-passport</a></td>
<td>Example of using the <a href="https://docs.strongloop.com/pages/viewpage.action?pageId=3836277">Third-party login (Passport) component</a>.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-ssl">loopback-example-ssl</a></td>
<td>SSL with LoopBack.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-embedded-relations">loopback-example-embedded-relations</a></td>
<td>Using embedded model relations.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-file-storage">loopback-example-file-storage</a></td>
<td>Storing and retrieving files using loopback-component-storage.</td>
</tr>

<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-middleware">loopback-example-middleware</a></td>
<td>Using middleware.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-operation-hooks">loopback-example-operation-hooks</a></td>
<td>Using operation hooks.</td>

<tr>
<td>
<a href="https://github.com/strongloop/loopback-example-user-management">loopback-example-user-management</a></td>
<td>How to register, log in / log out, and verify users; how to reset a user's password.</td>
</tr>
<tr>
<td>
<a href="https://github.com/strongloop/strong-gateway-demo">strong-gateway-demo</a></td>
<td>OAuth2 with StrongLoop API Gateway.</td>
</tr>
</tbody></table>

## Connector examples

These examples illustrate use of non-database connectors (see [loopback-example-database](https://github.com/strongloop/loopback-example-database) for example using database connectors).

<table><thead>
<tr>
<th width="300">Name </th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><a href="https://github.com/strongloop/loopback-example-rest-connector">loopback-example-rest-connector</a></td>
<td>Basic use of REST connector.</td>
</tr>
<tr>
<td><a href="https://github.com/strongloop/loopback-example-remote">loopback-example-remote</a></td>
<td>Basic use of the remote connector.</td>
</tr>

<tr>
<td><a href="https://github.com/strongloop/loopback-example-email">loopback-example-email</a></td>
<td>Sending email from a LoopBack app using the email connector.</td>
</tr>

<tr>
<td>
<a href="https://github.com/strongloop/loopback-connector-soap/tree/master/example">loopback-connector-soap</a></td>
<td>Example of SOAP connector.
<br/>NOTE: The example app is in the <code>example</code> directory.</td>
</tr>

</tbody></table>

## Client SDK examples

These examples illustrate using LoopBack's [client SDKs](https://docs.strongloop.com/display/LB/Client+SDKs).

<table><thead>
<tr>
<th width="300">Name </th>
<th>Description</th>
</tr>
</thead><tbody>
<tr><td>
<a href="https://github.com/strongloop/loopback-android-getting-started">loopback-android-getting-started</a></td>
<td>How to use the LoopBack Android SDK
</td></tr>
<tr><td>
<a href="https://github.com/strongloop/loopback-ios-getting-started">loopback-ios-getting-started</a></td>
<td>How to use the LoopBack iOS SDK
</td></tr>
<tr><td>
<a href="https://github.com/strongloop/loopback-example-angular">loopback-example-angular</a></td>
<td>Example using AngularJS client.</td>
</tr>
<tr><td>
<a href="https://github.com/strongloop/loopback-example-isomorphic">loopback-example-isomorphic</a></td>
<td>Using the LoopBack API on both client and server.</td>
</tr>
<tr>
<td><a href="https://github.com/strongloop/loopback-example-xamarin">loopback-example-xamarin</a></td>
<td>Using Xamarin SDK</td>
</tr>
</tbody></table>
