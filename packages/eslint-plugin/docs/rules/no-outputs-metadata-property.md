<!--

  DO NOT EDIT.

  This markdown file was autogenerated using a mixture of the following files as the source of truth for its data:
  - ../../src/rules/no-outputs-metadata-property.ts
  - ../../tests/rules/no-outputs-metadata-property/cases.ts

  In order to update this file, it is therefore those files which need to be updated, as well as potentially the generator script:
  - ../../../../tools/scripts/generate-rule-docs.ts

-->

# `@angular-eslint/no-outputs-metadata-property`

Disallows usage of the `outputs` metadata property. See more at https://angular.io/styleguide#style-05-12

- Type: suggestion
- Category: Best Practices

<br>

## Rule Options

The rule does not have any configuration options.

<br>

## Usage Examples

> The following examples are generated automatically from the actual unit tests within the plugin, so you can be assured that their behavior is accurate based on the current commit.

<br>

❌ - Examples of **incorrect** code for this rule:

```ts
@Component({
  outputs: [
  ~~~~~~~~~~
    'id: foo'
  ],
  ~
  selector: 'app-test'
})
class Test {}
```

```ts
@Directive({
  outputs: [
  ~~~~~~~~~~
    'id: foo'
  ],
  ~
  selector: 'app-test'
})
class Test {}
```

```ts
@Component({
  outputs,
  ~~~~~~~
})
class Test {}
```

```ts
@Directive({
  outputs: [],
  ~~~~~~~~~~~
})
class Test {}
```

```ts
const test = [];
@Component({
  'outputs': test,
  ~~~~~~~~~~~~~~~
})
class Test {}
```

```ts
@Directive({
  ['outputs']: undefined,
  ~~~~~~~~~~~~~~~~~~~~~~
})
class Test {}
```

```ts
function outputs() {
  return [];
}

@Component({
  [`outputs`]: outputs(),
  ~~~~~~~~~~~~~~~~~~~~~~
})
class Test {}
```

<br>

---

<br>

✅ - Examples of **correct** code for this rule:

```ts
class Test {}
```

```ts
@Component()
class Test {}
```

```ts
@Directive({})
class Test {}
```

```ts
const options = {};
@Component(options)
class Test {}
```

```ts
@Directive({
  selector: 'app-test',
  template: 'Hello'
})
class Test {}
```

```ts
@Component({
  selector: 'app-test',
  queries: {},
})
class Test {}
```

```ts
const outputs = 'providers';
@Directive({
  [outputs]: [],
})
class Test {}
```

```ts
@NgModule({
  bootstrap: [Foo]
})
class Test {}
```