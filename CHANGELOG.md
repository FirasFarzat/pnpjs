# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## 1.1.2 - 2018-07-06

### Added

- tooling: Setup Travis CI to process PRs and merges [[PR](https://github.com/pnp/pnpjs/pull/131)]
- tooling: Added support for --verbose flag when using gulp test
- documentation: Added article on deployment listing cdnjs urls [[PR](https://github.com/pnp/pnpjs/pull/145)]
- @pnp/nodejs: Support for local cloud authentication (China, Germany, US Gov) [[PR](https://github.com/pnp/pnpjs/pull/154)]

### Changed

- tooling: Updated travis test to use a custom mocha impl allowing for ignore timeouts [[PR](https://github.com/pnp/pnpjs/pull/136)]
- @pnp/pnpjs: Updated global variable name from $pnp -> pnp, docs updated to reflect change [[PR](https://github.com/pnp/pnpjs/pull/143)]
- @pnp/common: dateAdd timespan parameter now bound to custom string enumeration type
- documentation: Styling changes [[PR](https://github.com/pnp/pnpjs/pull/151)]
- @pnp/nodejs: SPFetchClient contructor realm parameter is now fifth [[PR](https://github.com/pnp/pnpjs/pull/154)]
- @pnp/sp: Added View, Views, and ViewFields to the exports [[PR](https://github.com/pnp/pnpjs/pull/155)]

### Fixed

- @pnp/sp: Fixed bug where parsing ClientSideText webpart from existing page included extra "</div>" [[PR](https://github.com/pnp/pnpjs/pull/129)]
- @pnp/sp: Changed return type of getPropertiesFor to be any instead of any[] [[PR](https://github.com/pnp/pnpjs/pull/130)]
- @pnp/sp: Fixed issue with decoding escaped json in ClientSidePage [[PR](https://github.com/pnp/pnpjs/pull/133)] [[PR](https://github.com/pnp/pnpjs/pull/150)]


## 1.1.1 - 2018-06-11

### Added

- @pnp/sp: Export UserProfileQuery from userprofiles ([@allanhvam](https://github.com/allanhvam)) [[PR](https://github.com/pnp/pnpjs/pull/123)]

### Fixed

- @pnp/nodejs: Fixed typo reported in #117 [[PR](https://github.com/pnp/pnpjs/pull/121)]
- tooling: Fixed path errors when building on non-Windows OS [[PR](https://github.com/pnp/pnpjs/pull/122)]

### Changed

- @pnp/sp-taxonomy: Updated default value for isAvailableForTagging when creating a team to true [[PR](https://github.com/pnp/pnpjs/pull/116)]

## 1.1.0 - 2018-05-29

### Added

- @pnp/sp-taxonomy: Added new library to support fluent queries against SharePoint Taxonomy data
- @pnp/sp-clientsvc: Added new library with fluent API base classes for client.svc based requests
- @pnp/common: Added utility method sanitizeGuid and getAttrValueFromString
- @pnp/odata: Added LambdaParser that takes any function to handle parsing Response
- tooling: Added --stats flag to gulp package to output webpack stats during bundle

### Fixed

- @pnp/odata: Fixed bug in BufferParser
- tooling: Fixed bug in serving individual packages using --p
- @pnp/sp: fixed issue in generated js files where $$VERSION$$ placeholder was not replaced correctly
- @pnp/graph: Disallowed caching of non-GET requests
- tooling: Fixed docs-clean ordering issue so everything is clean before other tasks run

### Changed

- @pnp/nodejs: Updated how global shims are set for Request types (Headers, Response, Request)
- @pnp/odata: Changes to request pipeline to support sp-clientsvc (non-breaking)
- @pnp/odata: Remove public get from abstract class Queryable (non-breaking)
- @pnp/sp: Added exports for toAbsoluteUrl and extractWebUrl utility methods
- @pnp/logging: Changed default LogLevel to Info for write and writeJSON
- build: Added preserveConstEnums flag to tsconfig.json
- docs: Small formatting changes, added anchors to headings in html to ease linking
- all: Updated package.json dependencies in root and individual packages
- docs: Updates to docs, added section on sp-taxonomy and sp-clientsvc libraries

### Removed

- @pnp/sp: Removed unused APIUrlException class
- @pnp/nodejs: Removed packaging step to webpack bundle, no need for node and reduces package size

### Deprecated

- @pnp/common: Deprecated exported static Util class. Migrate to using the individually exported methods

## 1.0.5 - 2018-05-11

### Added

- @pnp/sp: Added web's getParentWeb helper method [[PR](https://github.com/pnp/pnpjs/pull/74)]
- @pnp/sp: Added moveTo helper method for folder object [[PR](https://github.com/pnp/pnpjs/pull/75)]
- @pnp/sp: Added support for likes and comments on list items and modern pages [[PR](https://github.com/pnp/pnpjs/pull/85)]
- @pnp/sp: Added addClientSidePageByPath method to Web [[PR](https://github.com/pnp/pnpjs/pull/101)]
- @pnp/sp: Added getRootWeb method to Site [[PR](https://github.com/pnp/pnpjs/pull/102)]

### Fixed

- @pnp/nodejs: Fixed incorrect import for Request shims due to version change [[PR](https://github.com/pnp/pnpjs/pull/67)]
- @pnp/sp: Fixed docs for web example code [[PR](https://github.com/pnp/pnpjs/pull/72)]
- @pnp/config-store: Fixed docs and a bug in loading configuration [[PR](https://github.com/pnp/pnpjs/pull/73)]
- @pnp/sp: Fixed clientPeoplePickerSearchUser and clientPeoplePickerResolveUser methods running error with verbose OData mode [[PR](https://github.com/pnp/pnpjs/pull/79)]
- tooling: Fixed bug in gulp task test when using the --p flag .inactive.js test files were run [[PR](https://github.com/pnp/pnpjs/pull/85)]
- docs: Fixed import references ([@tarjeieo](https://github.com/tarjeieo)) [[PR](https://github.com/pnp/pnpjs/pull/87)]
- @pnp/odata: Updated all parsers to use same error handling code path [[PR](https://github.com/pnp/pnpjs/pull/90)]
- @pnp/sp: AddValidateUpdateItemUsingPath method [[PR](https://github.com/pnp/pnpjs/pull/89)]
- @pnp/sp: listItemAllFields object type fix [[PR](https://github.com/pnp/pnpjs/pull/98)]

### Changed

- @pnp/odata: Removed core.ts and moved code into parsers.ts to simplify [[PR](https://github.com/pnp/pnpjs/pull/90)]

## 1.0.4 - 2018-04-06

### Added

- @pnp/common: AdalClient for in-browser adal auth support. [[PR](https://github.com/pnp/pnpjs/pull/32)]
- @pnp/sp: Support for $expand in items.getAll ([@eirikb](https://github.com/eirikb)) [[PR](https://github.com/pnp/pnpjs/pull/33)]
- @pnp/odata: configureFrom method to queryable [[PR](https://github.com/pnp/pnpjs/pull/42)]
- @pnp/graph: Added basic support for onenote notebooks ([@olemp](https://github.com/olemp)) [[PR](https://github.com/pnp/pnpjs/pull/37)]
- @pnp/graph: Added basic support for users ([@olemp](https://github.com/olemp)) [[PR](https://github.com/pnp/pnpjs/pull/38)]
- @pnp/sp: Added support for ClientPeoplePickerWebServiceInterface ([@phawrylak](https://github.com/phawrylak)) [[PR](https://github.com/pnp/pnpjs/pull/43)]
- @pnp/sp: Added remove method to client side section, column, and part [[PR](https://github.com/pnp/pnpjs/pull/60)]
- @pnp/sp: Added setStorageEntity and removeStorageEntity & docs page [[PR](https://github.com/pnp/pnpjs/pull/64)]

### Changed

- @pnp/sp: Change search result properties to be enumerable [[PR](https://github.com/pnp/pnpjs/pull/41)]
- @pnp/nodejs: Updated docs for SPFetchClient
- @pnp/odata: Created a Queryable base class to serve as a generic base to ODataQueryable [[PR](https://github.com/pnp/pnpjs/pull/53)]
- all: Internally replaced import of Util with import of individual methods [[PR](https://github.com/pnp/pnpjs/pull/60)]
- all: Documentation updates
- @pnp/sp: Changed getStorageEntity return type to correct interface from string [[PR](https://github.com/pnp/pnpjs/pull/64)]
- all: update package.json dependencies


### Fixed

- all: Documentation fixes for typos [[PR](https://github.com/pnp/pnpjs/pull/26)]
- @pnp/graph: Typo in groups.calendar property name ([@olemp](https://github.com/olemp)) [[PR](https://github.com/pnp/pnpjs/pull/36)]
- @pnp/graph: Issue with graph.setup and fetchClientFactory [[PR](https://github.com/pnp/pnpjs/pull/32)]
- @pnp/sp: Issue where configuration options not passed to child calls in getPaged and getAll [[PR](https://github.com/pnp/pnpjs/pull/42)]
- @pnp/sp: Issue with matching last closing div when loading ClientText part ([@estruyf](https://github.com/estruyf)) [[PR](https://github.com/pnp/pnpjs/pull/47)]
- @pnp/nodejs: Issue with types.d.ts local dep [[PR](https://github.com/pnp/pnpjs/pull/50)]
- buildsystem: Issue where the $$Version$$ placeholder was not being replaced on build [[PR](https://github.com/pnp/pnpjs/pull/61)]

## 1.0.3 - 2018-03-05

### Added
- @pnp/sp: Support for backwards navigation in item paging skip method [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/sp: Support for % and # character in files and folders with the ResourcePath API [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/sp: Support for social follow API (_api/social.following) [[PR](https://github.com/pnp/pnpjs/pull/16)] [[Docs](./packages/sp/docs/social.md)]
- @pnp/sp: commentsDisabled property to ClientSidePage class [[PR](https://github.com/pnp/pnpjs/pull/18)] [[Docs](./packages/sp/docs/client-side-pages.md#control-comments)]
- @pnp/sp: Support for finding controls to ClientSidePage class [[PR](https://github.com/pnp/pnpjs/pull/19)] [[Docs](./packages/sp/docs/client-side-pages.md#find-controls)]
- @pnp/sp: Export ContentTypes and RegionalSettings related classes ([@allanhvam](https://github.com/allanhvam)) [[PR](https://github.com/pnp/pnpjs/pull/24)]


### Fixed
- @pnp/sp: Issue with File.setContentChunked and Files.addChunked in odata=verbose mode [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/sp: Issue with clone and configure [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/graph: Issue clone and configure [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/sp: Issue with adding client-side webparts with ids with {} chars [[PR](https://github.com/pnp/pnpjs/pull/16)]
- @pnp/sp: Issue with adding client-side webparts and setting order values [[PR](https://github.com/pnp/pnpjs/pull/17)]


## 1.0.2 : 2018-02-15

### Added
- @pnp/sp: Support for managing client-side pages [[PR](https://github.com/pnp/pnpjs/pull/7)]
- @pnp/sp: getAll method on Items collection [[PR](https://github.com/pnp/pnpjs/pull/4)]
- @pnp/sp: addUser, addLookup, addChoice, addMultiChoice, and addBoolean on Fields collection [[PR](https://github.com/pnp/pnpjs/pull/4)]
- @pnp/sp: getClientSideWebParts method on Web [[PR](https://github.com/pnp/pnpjs/pull/7)]
- tooling: updates to test gulp task to support --s and --site parameters [[PR](https://github.com/pnp/pnpjs/pull/7)]


### Changed
- Removed gulp-util in favor of individual libraries per guidance [[PR](https://github.com/pnp/pnpjs/pull/7)]

## 1.0.1 - 2018-01-22

### Added
- Everything
