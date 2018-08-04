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

## LIFT

## Locate

## Identify

## Flat

## T-DRY (Try to be DRY)

## Overall structural guidelines

## Folders-by-feature structure

## App root module

## Feature modules

## Shared feature module

## Core feature module

## Prevent re-import of the core module

## Lazy Loaded folders

## Never directly import lazy loaded folders

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
