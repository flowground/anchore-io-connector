# ![LOGO](logo.png) Anchore Engine API Server **flow**ground Connector

## Description

A generated **flow**ground connector for the Anchore Engine API Server API (version 0.1.9).

Generated from: https://api.apis.guru/v2/specs/anchore.io/0.1.9/swagger.json<br/>
Generated at: 2019-05-07T17:36:33+03:00

## API Description

This is the Anchore Engine API. Provides the primary external API for users of the service.

## Authorization

Supported authorization schemes:
- Basic Authentication

## Actions

### Simple status check

### List the account for the authenticated user

*Tags:* `Identity`

### List user summaries. Only available to the system admin user.

*Tags:* `User Management`

#### Input Parameters
* `state` - _optional_ - Filter accounts by state
    Possible values: active, disabled, deleting.

### Create a new user. Only avaialble to admin user.

*Tags:* `User Management`

### Delete the specified account, only allowed if the account is in the disabled state. All users will be deleted along with the account and all resources will be garbage collected

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_

### Get info about an user. Only available to admin user. Uses the main user Id, not a username.

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_

### Update the state of an account to either enabled or disabled. For deletion use the DELETE route

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_

### List accounts for the user

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_

### Create a new user

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_

### Delete a specific user credential by username of the credential. Cannot be the credential used to authenticate the request.

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_
* `username` - _required_

### Get a specific user in the specified account

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_
* `username` - _required_

### Delete a credential by type

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_
* `username` - _required_
* `credential_type` - _required_
    Possible values: password.

### Get current credential summary

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_
* `username` - _required_

### add/replace credential

*Tags:* `User Management`

#### Input Parameters
* `accountname` - _required_
* `username` - _required_

### Delete Events

> Delete all or a subset of events filtered using the optional query parameters

*Tags:* `Events`

#### Input Parameters
* `before` - _optional_ - Delete events that occurred before the timestamp
* `since` - _optional_ - Delete events that occurred after the timestamp
* `level` - _optional_ - Delete events that match the level - INFO or ERROR
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List Events

> Returns a paginated list of events in the descending order of their occurrence. Optional query parameters may be used for filtering results

*Tags:* `Events`

#### Input Parameters
* `source_servicename` - _optional_ - Filter events by the originating service
* `source_hostid` - _optional_ - Filter events by the originating host ID
* `resource_type` - _optional_ - Filter events by the type of resource - tag, imageDigest, repository etc
* `resource_id` - _optional_ - Filter events by the id of the resource
* `level` - _optional_ - Filter events by the level - INFO or ERROR
* `since` - _optional_ - Return events that occurred after the timestamp
* `before` - _optional_ - Return events that occurred before the timestamp
* `page` - _optional_ - Pagination controls - return the nth page of results. Defaults to first page if left empty
* `limit` - _optional_ - Number of events in the result set. Defaults to 100 if left empty
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete Event

> Delete an event by its event ID

*Tags:* `Events`

#### Input Parameters
* `eventId` - _required_ - Event ID of the event to be deleted
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get Event

> Lookup an event by its event ID

*Tags:* `Events`

#### Input Parameters
* `eventId` - _required_ - Event ID of the event for lookup
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Health check, returns 200 and no body if service is running

### Import and image analysis directly

*Tags:* `Images`

#### Input Parameters
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List all visible images

> List all images visible to the user

*Tags:* `Images`

#### Input Parameters
* `history` - _optional_ - Include image history in the response
* `fulltag` - _optional_ - Full docker-pull string to filter results by (e.g. docker.io/library/nginx:latest, or myhost.com:5000/testimages:v1.1.1)
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Submit a new image for analysis by the engine

> Creates a new analysis task that is executed asynchronously

*Tags:* `Images`

#### Input Parameters
* `force` - _optional_ - Override any existing entry in the system
* `autosubscribe` - _optional_ - Instruct engine to automatically begin watching the added tag for updates from registry
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete image by docker imageId

*Tags:* `Images`

#### Input Parameters
* `imageId` - _required_
* `force` - _optional_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Lookup image by docker imageId

*Tags:* `Images`

#### Input Parameters
* `imageId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Check policy evaluation status for image

> Get the policy evaluation for the given image

*Tags:* `Images` `Policy Evaluation`

#### Input Parameters
* `imageId` - _required_
* `policyId` - _optional_
* `tag` - _required_
* `detail` - _optional_
* `history` - _optional_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List image content types

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type files

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type java

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageId` - _required_
* `ctype` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get vulnerability types

*Tags:* `Images` `Vulnerabilities` `Queries`

#### Input Parameters
* `imageId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get vulnerabilities by type

*Tags:* `Images` `Vulnerabilities` `Queries`

#### Input Parameters
* `imageId` - _required_
* `vtype` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete an image analysis

*Tags:* `Images`

#### Input Parameters
* `imageDigest` - _required_
* `force` - _optional_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get image metadata

*Tags:* `Images`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Check policy evaluation status for image

> Get the policy evaluation for the given image

*Tags:* `Images` `Policy Evaluation`

#### Input Parameters
* `imageDigest` - _required_
* `policyId` - _optional_
* `tag` - _required_
* `detail` - _optional_
* `history` - _optional_
* `interactive` - _optional_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List image content types

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type files

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type java

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the content of an image by type

*Tags:* `Images` `Image Content` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `ctype` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List image metadata types

*Tags:* `Images` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get the metadata of an image by type

*Tags:* `Images` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `mtype` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get vulnerability types

*Tags:* `Images` `Vulnerabilities` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get vulnerabilities by type

*Tags:* `Images` `Vulnerabilities` `Queries`

#### Input Parameters
* `imageDigest` - _required_
* `vtype` - _required_
* `force_refresh` - _optional_
* `vendor_only` - _optional_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List policies

> List all saved policy bundles

*Tags:* `Policies`

#### Input Parameters
* `detail` - _optional_ - Include policy bundle detail in the form of the full bundle content for each entry
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Add a new policy

> Adds a new policy bundle to the system

*Tags:* `Policies`

#### Input Parameters
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete policy

> Delete the specified policy

*Tags:* `Policies`

#### Input Parameters
* `policyId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get specific policy

> Get the policy bundle content

*Tags:* `Policies`

#### Input Parameters
* `policyId` - _required_
* `detail` - _optional_ - Include policy bundle detail in the form of the full bundle content for each entry
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Update policy

> Update/replace and existing policy

*Tags:* `Policies`

#### Input Parameters
* `policyId` - _required_
* `active` - _optional_ - Mark policy as active
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List of images containing given package

> Filterable query interface to search for images containing specified package

*Tags:* `Queries`

#### Input Parameters
* `name` - _required_ - Name of package to search for (e.g. sed)
* `package_type` - _optional_ - Type of package to filter on (e.g. dpkg)
* `version` - _optional_ - Version of named package to filter on (e.g. 4.4-1)
* `page` - _optional_ - The page of results to fetch. Pages start at 1
* `limit` - _optional_ - Limit the number of records for the requested page. If omitted or set to 0, return all results in a single page
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List images vulnerable to the specific vulnerability ID.

> Returns a listing of images and their respective packages vulnerable to the given vulnerability ID

*Tags:* `Vulnerabilities` `Queries`

#### Input Parameters
* `vulnerability_id` - _required_ - The ID of the vulnerability to search for within all images stored in anchore-engine (e.g. CVE-1999-0001)
* `namespace` - _optional_ - Filter results to images within the given vulnerability namespace (e.g. debian:8, ubuntu:14.04)
* `affected_package` - _optional_ - Filter results to images with vulnable packages with the given package name (e.g. libssl)
* `severity` - _optional_ - Filter results to vulnerable package/vulnerability with the given severity
    Possible values: Unknown, Negligible, Low, Medium, High, Critical.
* `vendor_only` - _optional_ - Filter results to include only vulnerabilities that are not marked as invalid by upstream OS vendor data
* `page` - _optional_ - The page of results to fetch. Pages start at 1
* `limit` - _optional_ - Limit the number of records for the requested page. If omitted or set to 0, return all results in a single page
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Listing information about given vulnerability

> List (w/filters) vulnerability records known by the system, with affected packages information if present

*Tags:* `Vulnerabilities` `Queries`

#### Input Parameters
* `id` - _required_ - The ID of the vulnerability (e.g. CVE-1999-0001)
* `affected_package` - _optional_ - Filter results by specified package name (e.g. sed)
* `affected_package_version` - _optional_ - Filter results by specified package version (e.g. 4.4-1)
* `page` - _optional_ - The page of results to fetch. Pages start at 1
* `limit` - _optional_ - Limit the number of records for the requested page. If omitted or set to 0, return all results in a single page

### List configured registries

> List all configured registries the system can/will watch

*Tags:* `Registries`

#### Input Parameters
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Add a new registry

> Adds a new registry to the system

*Tags:* `Registries`

#### Input Parameters
* `validate` - _optional_ - flag to determine whether or not to validate registry/credential at registry add time
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete a registry configuration

> Delete a registry configuration record from the system. Does not remove any images.

*Tags:* `Registries`

#### Input Parameters
* `registry` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get a specific registry configuration

> Get information on a specific registry

*Tags:* `Registries`

#### Input Parameters
* `registry` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Update/replace a registry configuration

> Replaces an existing registry record with the given record

*Tags:* `Registries`

#### Input Parameters
* `registry` - _required_
* `validate` - _optional_ - flag to determine whether or not to validate registry/credential at registry update time
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Add repository to watch

*Tags:* `Repository Credentials`

#### Input Parameters
* `repository` - _required_ - full repository to add e.g. docker.io/library/alpine
* `autosubscribe` - _optional_ - flag to enable/disable auto tag_update activation when new images from a repo are added
* `lookuptag` - _optional_ - use specified existing tag to perform repo scan (default is 'latest')
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Service status

> Get the API service status

*Tags:* `System`

### List all subscriptions

*Tags:* `Subscriptions`

#### Input Parameters
* `subscription_key` - _optional_ - filter only subscriptions matching key
* `subscription_type` - _optional_ - filter only subscriptions matching type
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Add a subscription of a specific type

> Create a new subscription to watch a tag and get notifications of changes

*Tags:* `Subscriptions`

#### Input Parameters
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Delete subscriptions of a specific type

*Tags:* `Subscriptions`

#### Input Parameters
* `subscriptionId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Get a specific subscription set

*Tags:* `Subscriptions`

#### Input Parameters
* `subscriptionId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### Update an existing and specific subscription

*Tags:* `Subscriptions`

#### Input Parameters
* `subscriptionId` - _required_
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### List all visible image digests and tags

> List all image tags visible to the user

*Tags:* `Summaries`

#### Input Parameters
* `x-anchore-account` - _optional_ - An account name to change the resource scope of the request to that account, if permissions allow (admin only)

### System status

> Get the system status including queue lengths

*Tags:* `System`

### list feeds operations and information

*Tags:* `System`

### trigger feeds operations

*Tags:* `System`

#### Input Parameters
* `flush` - _optional_ - instruct system to flush existing data feeds records from anchore-engine
* `sync` - _optional_ - instruct system to re-sync data feeds

### Describe the policy language spec implemented by this service.

> Get the policy language spec for this service

*Tags:* `System` `Policy`

### List system services

*Tags:* `System` `Services`

### Get a service configuration and state

*Tags:* `System` `Services`

#### Input Parameters
* `servicename` - _required_

### Delete the service config

*Tags:* `System` `Services`

#### Input Parameters
* `servicename` - _required_
* `hostid` - _required_

### Get service config for a specific host

*Tags:* `System` `Services`

#### Input Parameters
* `servicename` - _required_
* `hostid` - _required_

### List authenticated user info

*Tags:* `Identity`

### Get current credential summary

*Tags:* `Identity`

### add/replace credential

*Tags:* `Identity`

### Returns the version object for the service, including db schema version info

## License

**flow**ground :- Telekom iPaaS / anchore-io-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
