# [`jayschema`](https://github.com/natesilva/jayschema) - test summary

# All validators fail this test

`some languages do not distinguish between different types of numeric value, a float is not an integer even without fractional part`

# [`jayschema`](https://github.com/natesilva/jayschema) failed tests

Some validators have deliberately chosen not to support parts of the spec. Go to the [`jayschema`](https://github.com/natesilva/jayschema) homepage to learn if
that is the case for these tests.

|test failed|reason
|-----------|------
|`maxLength validation, two supplementary Unicode code points is long enough`|Expected result: `true` but validator returned: `false`
|`minLength validation, one supplementary Unicode code point is not long enough`|Expected result: `false` but validator returned: `true`
|`validation of URIs, an invalid URI though valid URI reference`|Expected result: `false` but validator returned: `true`
|`property named $ref that is not a reference, property named $ref valid`|Expected result: `true` but validator returned: `"uri.slice is not a function"`. **This excludes this validator from performance tests**
|`property named $ref that is not a reference, property named $ref invalid`|Expected result: `false` but validator returned: `"uri.slice is not a function"`. **This excludes this validator from performance tests**
|`remote ref, remote ref valid`|Expected result: `true` but validator returned: `false`
|`fragment within remote ref, remote fragment valid`|Expected result: `true` but validator returned: `"Cannot convert undefined or null to object"`
|`fragment within remote ref, remote fragment invalid`|Expected result: `false` but validator returned: `"Cannot convert undefined or null to object"`
|`ref within remote ref, ref within ref valid`|Expected result: `true` but validator returned: `"Cannot convert undefined or null to object"`
|`ref within remote ref, ref within ref invalid`|Expected result: `false` but validator returned: `"Cannot convert undefined or null to object"`
|`change resolution scope, changed scope ref valid`|Expected result: `true` but validator returned: `false`

**All other tests passed**.

[back to benchmarks](https://github.com/ebdrup/json-schema-benchmark)