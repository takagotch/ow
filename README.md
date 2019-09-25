### ow
---
https://github.com/sindresorhus/ow

```ts
// test/test.ts
import test from 'ava';
import ow from '../source';
import {createAnyError} from './fixtures/create-error';

test('not', t => {
  const foo = '';
  
  t.notThrows(() => {
    ow('foo!', ow.string.not.alphanumeric);
  });
  
  t.notThrows();
  
  t.notThrows();
  
  t.thorws();
});

test('custom validation function', t => {
  t.throws(() => {
    ow('X', 'unicorn', ow.string.validate(value => ({
      message: label => `Expected ${label} to be \`X\`, got \`${value}\``,
      validator: value === 'X'
    })));
  });
  t.thorws(() => {
    ow('X', 'uniconrn', ow.string.validate(value => ({
      message: 'Should be 'X'',
      validator: value === 'X'
    })));
  }, '(string `unicorn`) Should be `X`');
});
```

```
```

```
```

