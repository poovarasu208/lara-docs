#Nova
- [Introduction](#introduction)
- [Resource Management](#resource-management)
- [Actions](#actions)
- [Filters](#filters)
- [Lenses](#lenses)
- [Metrics](#metrics)
- [Authorization](#authorization)
- [Scout Search Integration](#scout-search-integration)

<a name="introduction"></a>
## Introduction

[Nova](https://nova.laravel.com/) is a beautifully designed administration panel for Laravel. Carefully crafted by the creators of Laravel to make you the most productive developer in the galaxy.
 
<a name="resource-management"></a>
## Resource Management

At the heart of Nova is [resource management:](https://nova.laravel.com/docs/1.0/resources/#defining-resources) the ability to create, read, update, and delete resources. Not only does Nova cover basic resource management, it also covers things like updating data on things like polymorphic relationships.

Each eloquent model in your project will have a corresponding Nova resource which defines fields, actions, filters, lenses, and cards. Nova does not store any configuration in the database, it is configured using simple PHP classes.

Nova has basic field types as well as custom types like Markdown, Trix, Code, and Place.

<a name="actions"></a>
## Actions

[Actions](https://nova.laravel.com/docs/1.0/actions/defining-actions.html) are simple PHP classes performing a task on resources. For example, if you wanted the ability to deactivate a user, you could define an action and trigger it from the UI on one user or a batch of users. If a model is marked with an Actionable trait, Nova provides an audit trail of the actions performed against that model and tracks who triggered the action.

<a name="filters"></a>
## Filters

[Filters](https://nova.laravel.com/docs/1.0/filters/defining-filters.html) allow you to scope resources for index queries on things like “active users” or “suspended accounts.” Similar to actions, filters are defined as simple PHP classes that enable you to scope your queries with the query builder. The filters are available from the index view of a given resource as well as when displayed as a relationship.

<a name="lenses"></a>
## Lenses

[Lenses](https://nova.laravel.com/docs/1.0/lenses/defining-lenses.html) allow you to build different views for a resource with full control over the underlying query and fields returned. When lenses are defined and attached to a resource, they can be used on a resource’s index page.

<a name="metrics"></a>
## Metrics

Nova ships with three standard [metrics:](https://nova.laravel.com/docs/1.0/metrics/defining-metrics.html) value, trend, and partition. The built-in metric functionality makes it really easy to generate metrics. For example, you could track the number of new users created in your application for the current quarter compared to last quarter.

Once a metric is defined on a resource, it’s available from the index of the resource view. You can also create trends very easily leveraging the underlying Nova trends logic, and you can display them in various increments such as minute, hour, week, or even month.

<a name="authorization"></a>
## [Authorization](https://nova.laravel.com/docs/1.0/resources/authorization.html)

Nova integrates with Laravel policies, and you have granular control over how is allowed to manage resources. When an Eloquent model has a policy, Nova uses it to authorize resource actions. You also have full control over which users can attach resources together via relationships.

<a name="scout-search-integration"></a>
## [Scout Search Integration](https://nova.laravel.com/docs/1.0/search/scout-integration.html)

Nova includes search functionality using SQL queries by default, and also seamlessly integrates with Laravel Scout if your application leverages scout.

Another area where the search is really cool is when you are creating a resource, that belongs to another model, Nova provides a search input to quickly find the related model.
