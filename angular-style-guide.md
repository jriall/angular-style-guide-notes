# Angular Style Guide

Notes from the official Angular Style Guide - https://angular.io/guide/styleguide

## Single responsibility

Apply the single responsibility principle (SRP) to all components, services, and other  symbols. This helps make the app cleaner, easier to read and maintain, and more testable.

### Rule of One

**Do** define one thing, such as a service or component, per file.

**Consider** limiting files to 400 lines of code.

### Small functions

**Do** define small functions

**Consider** limiting to no more than 75 lines.

## Naming

Naming conventions are hugely important to maintainability and readability. This guide recommends naming conventions for the file name and the symbol name.

### General Naming Guidelines

**Do** use consistent names for all symbols.

**Do** follow a pattern that describes the symbol's feature then its type. The recommended pattern is `feature.type.ts`.

### Separate file names with dots and dashes

**Do** use dashes to separate words in the descriptive name.

**Do** use dots to separate the descriptive name from the type.

**Do** use consistent type names for all components following a pattern that describes the component's feature then its type. A recommended pattern is `feature.type.ts`.

**Do** use conventional type names including `.service`, `.component`, `.pipe`, `.module`, and `.directive`. Invent additional type names if you must but take care not to create too many.

### Symbols and file names

**Do** use consistent names for all assets named after what they represent.

**Do** use upper camel case for class names.

**Do** match the name of the symbol to the name of the file.

**Do** append the symbol name with the conventional suffix (such as `Component`, `Directive`, `Module`, `Pipe`, or `Service`) for a thing of that type.

**Do** give the filename the conventional suffix (such as `.component.ts`, `.directive.ts`, `.module.ts`, `.pipe.ts`, or `.service.ts`) for a file of that type.

### Service names

**Do** use consistent names for all services named after their feature.

**Do** suffix a service class name with Service. For example, something that gets data or heroes should be called a DataService or a HeroService.

A few terms are unambiguously services. They typically indicate agency by ending in "-er". You may prefer to name a service that logs messages `Logger` rather than `LoggerService`. Decide if this exception is agreeable in your project. As always, strive for consistency.

### Bootstrapping

**Do** put bootstrapping and platform logic for the app in a file named `main.ts`.

**Do** include error handling in the bootstrapping logic.

Avoid putting app logic in `main.ts`. Instead, consider placing it in a component or service.

### Component selectors

**Do** use dashed-case or kebab-case for naming the element selectors of components.

Correct usage:

```
@Component({
  selector: 'toh-hero-button',
  templateUrl: './hero-button.component.html'
})
export class HeroButtonComponent {}
```

### Component custom prefix

**Do** use a hyphenated, lowercase element selector value (e.g. `admin-users`).

**Do** use a custom prefix for a component selector. For example, the prefix `toh` represents from Tour of Heroes and the prefix `admin` represents an admin feature area.

**Do** use a prefix that identifies the feature area or the app itself.

### Directive selectors

**Do** Use lower camel case for naming the selectors of directives.

### Directive custom prefix

**Do** use a custom prefix for the selector of directives (e.g, the prefix `toh` from Tour of Heroes).

**Do** spell non-element selectors in lower camel case unless the selector is meant to match a native HTML attribute.

### Pipe names

**Do** use consistent names for all pipes, named after their feature.

### Unit test file names

**Do** name test specification files the same as the component they test.

**Do** name test specification files with a suffix of `.spec`.

Correct examples:

`heroes.component.spec.ts`
`logger.service.spec.ts`
`ellipsis.pipe.spec.ts`

### End-to-End (E2E) test file names

Do name end-to-end test specification files after the feature they test with a suffix of `.e2e-spec`.

Correct examples:

`app.e2e-spec.ts`
`heroes.e2e-spec.ts`

### Angular NgModule names

**Do** append the symbol name with the suffix Module.

**Do** give the file name the `.module.ts` extension.

**Do** name the module after the feature and folder it resides in.

**Do** suffix a *RoutingModule* class name with `RoutingModule`.

**Do** end the filename of a *RoutingModule* with `-routing.module.ts`.

## Coding conventions

### Classes

**Do** use upper camel case when naming classes.

### Constants

**Do** declare variables with `const` if their values should not change during the application lifetime.

**Consider** spelling const variables in lower camel case.

**Why?** Lower camel case variable names (`heroRoutes`) are easier to read and understand than the traditional UPPER_SNAKE_CASE names (`HERO_ROUTES`).

**Why?** The tradition of naming constants in UPPER_SNAKE_CASE reflects an era before the modern IDEs that quickly reveal the `const` declaration. TypeScript prevents accidental reassignment.

**Do** tolerate existing `const` variables that are spelled in UPPER_SNAKE_CASE.

**Why?** The tradition of UPPER_SNAKE_CASE remains popular and pervasive, especially in third party modules. It is rarely worth the effort to change them at the risk of breaking existing code and documentation.

### Interfaces

**Do** name an interface using upper camel case.

**Consider** naming an interface without an `I` prefix.

**Consider** using a class instead of an interface for services and declarables (components, directives, and pipes).

**Consider** using an interface for data models.

### Properties and methods

**Do** use lower camel case to name properties and methods.

**Avoid** prefixing private properties and methods with an underscore.

### Import line spacing

**Consider** leaving one empty line between third party imports and application imports.

**Consider** listing import lines alphabetized by the module.

**Consider** listing destructured imported symbols alphabetically.

## Application structure and NgModules

Have a near-term view of implementation and a long-term vision. Start small but keep in mind where the app is heading down the road.

All of the app's code goes in a folder named `src`. All feature areas are in their own folder, with their own NgModule.

All content is one asset per file. Each component, service, and pipe is in its own file. All third party vendor scripts are stored in another folder and not in the `src` folder. You didn't write them and you don't want them cluttering src. Use the naming conventions for files in this guide.

### *LIFT*

**Do** structure the app such that you can Locate code quickly, Identify the code at a glance, keep the Flattest structure you can, and Try to be DRY.

**Do** define the structure to follow these four basic guidelines, listed in order of importance.

### Locate

**Do** make locating code intuitive, simple and fast.

### Identify

**Do** name the file such that you instantly know what it contains and represents.

**Do** be descriptive with file names and keep the contents of the file to exactly one component.

**Avoid** files with multiple components, multiple services, or a mixture.

### Flat

**Do** keep a flat folder structure as long as possible.

**Consider** creating sub-folders when a folder reaches seven or more files.

**Consider** configuring the IDE to hide distracting, irrelevant files such as generated `.js` and `.js.map` files.

### T-DRY (Try to be DRY)

**Do** be DRY (Don't Repeat Yourself).

**Avoid** being so DRY that you sacrifice readability.

### Overall structural guidelines

**Do** start small but keep in mind where the app is heading down the road.

**Do** have a near term view of implementation and a long term vision.

**Do** put all of the app's code in a folder named src.

**Consider** creating a folder for a component when it has multiple accompanying files (`.ts`, `.html`, `.css` and `.spec`).

### Folders-by-feature structure

**Do** create folders named for the feature area they represent.

**Do** create an NgModule for each feature area.

### App root module

**Do** create an NgModule in the app's root folder, for example, in `/src/app`.

**Consider** naming the root module `app.module.ts`.

### Feature modules

**Do** create an NgModule for all distinct features in an application; for example, a `Heroes` feature.

**Do** place the feature module in the same named folder as the feature area; for example, in `app/heroes`.

**Do** name the feature module file reflecting the name of the feature area and folder; for example, `app/heroes/heroes.module.ts`.

**Do** name the feature module symbol reflecting the name of the feature area, folder, and file; for example, `app/heroes/heroes.module.ts` defines `HeroesModule`.

### Shared feature module

**Do** create a feature module named `SharedModule` in a shared folder; for example, `app/shared/shared.module.ts` defines `SharedModule`.

**Do** declare components, directives, and pipes in a shared module when those items will be re-used and referenced by the components declared in other feature modules.

**Consider** using the name `SharedModule` when the contents of a shared module are referenced across the entire application.

**Consider** not providing services in shared modules. Services are usually singletons that are provided once for the entire application or in a particular feature module. There are exceptions, however. For example, in the sample code that follows, notice that the `SharedModule` provides `FilterTextService`. This is acceptable here because the service is stateless; that is, the consumers of the service aren't impacted by new instances.

**Do** import all modules required by the assets in the `SharedModule`; for example, `CommonModule` and `FormsModule`.

**Do declare all components, directives, and pipes in the `SharedModule`.

**Do** export all symbols from the `SharedModule` that other feature modules need to use.

**Avoid** specifying app-wide singleton providers in a `SharedModule`. Intentional singletons are OK. Take care.

### Core feature module

**Consider** collecting numerous, auxiliary, single-use classes inside a core module to simplify the apparent structure of a feature module.

**Consider** calling the application-wide core module, `CoreModule`. Importing `CoreModule` into the root `AppModule` reduces its complexity and emphasizes its role as orchestrator of the application as a whole.

**Do** create a feature module named `CoreModule` in a core folder (e.g. app/core/core.module.ts defines `CoreModule`).

**Do** put a singleton service whose instance will be shared throughout the application in the `CoreModule` (e.g. `ExceptionService` and `LoggerService`).

**Do** import all modules required by the assets in the `CoreModule` (e.g. `CommonModule` and `FormsModule`).

**Do** gather application-wide, single use components in the `CoreModule`. Import it once (in the `AppModule`) when the app starts and never import it anywhere else. (e.g. `NavComponent` and `SpinnerComponent`).

**Avoid** importing the `CoreModule` anywhere except in the `AppModule`.

**Do** export all symbols from the `CoreModule` that the `AppModule` will import and make available for other feature modules to use.

### Prevent re-import of the core module

Only the root `AppModule` should import the `CoreModule`.

Do guard against reimporting of `CoreModule` and fail fast by adding guard logic.

Example of how to do so below:

```
app/core/module-import-guard.ts

export function throwIfAlreadyLoaded(parentModule: any, moduleName: string) {
  if (parentModule) {
    throw new Error(`${moduleName} has already been loaded. Import Core modules in the AppModule only.`);
  }
}
```
```
app/core/core.module.ts

import { NgModule, Optional, SkipSelf } from '@angular/core';
import { CommonModule } from '@angular/common';

import { LoggerService } from './logger.service';
import { NavComponent } from './nav/nav.component';
import { throwIfAlreadyLoaded } from './module-import-guard';

@NgModule({
  imports: [
    CommonModule // we use ngFor
  ],
  exports: [NavComponent],
  declarations: [NavComponent],
  providers: [LoggerService]
})
export class CoreModule {
  constructor( @Optional() @SkipSelf() parentModule: CoreModule) {
    throwIfAlreadyLoaded(parentModule, 'CoreModule');
  }
}
```

### Lazy Loaded folders

A distinct application feature or workflow may be *lazy loaded* or *loaded on demand* rather than when the application starts.

Do put the contents of *lazy loaded* features in a *lazy loaded* folder. A typical *lazy loaded* folder contains a *routing component*, its child components, and their related assets and modules.

## Never directly import lazy loaded folders

**Avoid** allowing modules in sibling and parent folders to directly import a module in a *lazy loaded feature*.

**Why?** Directly importing and using a module will load it immediately when the intention is to load it on demand.

## Components

## Components as elements

## Extract templates and styles to their own files

## Decorate input and output properties

## Avoid aliasing inputs and outputs

## Member sequence

## Delegate complex component logic to services

## Don't prefix output properties

## Put presentation logic in the component class

## Directives

## Use directives to enhance an element

## HostListener/HostBinding decorators versus host metadata

## Services

## Services are singletons

## Single responsibility

## Providing a service

## Use the @Injectable() class decorator

## Data Services

## Talk to the server through a service

## Lifecycle hooks

## Implement lifecycle hook interfaces

## Appendix

## Codelyzer

## File templates and snippets
