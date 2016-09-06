# [`jjv`](https://github.com/acornejo/jjv) - test summary

# All validators fail this test

`some languages do not distinguish between different types of numeric value, a float is not an integer even without fractional part`

# [`jjv`](https://github.com/acornejo/jjv) failed tests

Some validators have deliberately chosen not to support parts of the spec. Go to the [`jjv`](https://github.com/acornejo/jjv) homepage to learn if
that is the case for these tests.

|test failed|reason
|-----------|------
|`maxLength validation, two supplementary Unicode code points is long enough`|Expected result: `true` but validator returned: `false`
|`minLength validation, one supplementary Unicode code point is not long enough`|Expected result: `false` but validator returned: `true`
|`escaped pointer ref, slash valid`|Expected result: `true` but validator returned: `false`. **This excludes this validator from performance tests**
|`escaped pointer ref, tilda valid`|Expected result: `true` but validator returned: `false`. **This excludes this validator from performance tests**
|`escaped pointer ref, percent valid`|Expected result: `true` but validator returned: `false`. **This excludes this validator from performance tests**
|`change resolution scope, changed scope ref valid`|Expected result: `true` but validator returned: `false`
|`required validation, ignores non-objects`|Expected result: `true` but validator returned: `false`. **This excludes this validator from performance tests**

**All other tests passed**.

[back to benchmarks](https://github.com/ebdrup/json-schema-benchmark)