# json-schema-benchmark
Performance benchmark for Node.js JSON-schema validators.

Also tests against [official JSON-schema test suite](https://github.com/json-schema/JSON-Schema-Test-Suite) and checks
for validators that cause side-effects on schema or data.

[Contribute to these benchmarks](https://github.com/ebdrup/json-schema-benchmark/blob/master/CONTRIBUTING.md)

# Performance

![performance](https://chart.googleapis.com/chart?chxt=x,y&cht=bhs&chco=76A4FB&chls=2.0&chbh=36,4,1&chs=600x420&chxl=-1:|ajv|is-my-json-valid|jsen|schemasaurus|themis|z-schema|jsck|skeemas|jsonschema|tv4&chd=t:100,65.9,61.1,22.1,17.5,5.8,2.5,0.7,0.7,0.4)

|Validator|Relative speed|Number of test runs per second|
|---------|:------------:|:----------------------------:|
|[`ajv`](https://github.com/epoberezkin/ajv)|100%|9937 (± 6.12%)|
|[`is-my-json-valid`](https://github.com/mafintosh/is-my-json-valid)|65.9%|6552 (± 2.64%)|
|[`jsen`](https://github.com/bugventure/jsen)|61.1%|6073 (± 1.57%)|
|[`schemasaurus`](https://github.com/AlexeyGrishin/schemasaurus)|22.1%|2192 (± 6.77%)|
|[`themis`](https://github.com/playlyfe/themis)|17.5%|1740 (± 3.82%)|
|[`z-schema`](https://github.com/zaggino/z-schema)|5.8%|579 (± 0.55%)|
|[`jsck`](https://github.com/pandastrike/jsck#readme)|2.5%|246 (± 3.56%)|
|[`skeemas`](https://github.com/Prestaul/skeemas#readme)|0.7%|68 (± 0.46%)|
|[`jsonschema`](https://github.com/tdegrunt/jsonschema#readme)|0.7%|65 (± 1.04%)|
|tv4|0.4%|43 (± 0.69%)|

235 tests are run in each test run.

Validators tested: [`is-my-json-valid (2.13.1)`](https://github.com/mafintosh/is-my-json-valid), [`jsen (0.6.1)`](https://github.com/bugventure/jsen), [`ajv (4.6.1)`](https://github.com/epoberezkin/ajv), [`themis (1.1.6)`](https://github.com/playlyfe/themis), [`z-schema (3.17.0)`](https://github.com/zaggino/z-schema), [`jjv (1.0.2)`](https://github.com/acornejo/jjv), [`skeemas (1.2.2)`](https://github.com/Prestaul/skeemas#readme), [`jayschema (0.3.1)`](https://github.com/natesilva/jayschema), [`schemasaurus (0.7.8)`](https://github.com/AlexeyGrishin/schemasaurus), [`jsck (0.3.0)`](https://github.com/pandastrike/jsck#readme), [`jassi (0.1.2)`](https://github.com/iclanzan/jassi), [`JSV (4.0.2)`](http://github.com/garycourt/JSV), [`request-validator (0.3.3)`](https://github.com/bugventure/request-validator), [`json-gate (0.8.22)`](https://github.com/oferei/json-gate), [`json-model (0.2.24)`](https://github.com/geraintluff/json-model), tv4, [`jsonschema (1.1.0)`](https://github.com/tdegrunt/jsonschema#readme), [`revalidator (0.3.1)`](https://github.com/flatiron/revalidator), 

(validators not in the results above where excluded because of failing tests - see below for details)

[`ajv`](https://github.com/epoberezkin/ajv) is currently the fastest JSON-schema validator out there.

The fastest validator has 100%, the rest a lower score relative to the fastest.
If a validator has a score of 5% that means that it's speed is 5% of the fastest,
meaning that it's 20 times slower than the fastest.

# Test failure summary

This test suite uses the [official JSON-schema test suite](https://github.com/json-schema/JSON-Schema-Test-Suite).

If a validator does not pass a test in the official test suite, it will show up in these results.

![failing tests](https://chart.googleapis.com/chart?chxt=x,y&cht=bhs&chco=76A4FB&chls=2.0&chbh=18,4,1&chs=600x416&chxl=-1:|ajv|skeemas|z-schema|jsonschema|is-my-json-valid|jjv|jsen|jayschema|themis|schemasaurus|jsck|tv4|request-validator|jassi|json-model|JSV|json-gate|revalidator&chd=t:1,2,3,4,8,8,11,12,14,16,18,24,29,31,40,58,72,140&chxr=0,0,140&chds=0,140)

|Validator|Number of failing tests (click for details)|
|---------|-----------------------|
|[`ajv`](https://github.com/epoberezkin/ajv)|[1](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/ajv.md)|
|[`skeemas`](https://github.com/Prestaul/skeemas#readme)|[2](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/skeemas.md)|
|[`z-schema`](https://github.com/zaggino/z-schema)|[3](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/z-schema.md)|
|[`jsonschema`](https://github.com/tdegrunt/jsonschema#readme)|[4](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jsonschema.md)|
|[`is-my-json-valid`](https://github.com/mafintosh/is-my-json-valid)|[8](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/is-my-json-valid.md)|
|[`jjv`](https://github.com/acornejo/jjv)|[8](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jjv.md)|
|[`jsen`](https://github.com/bugventure/jsen)|[11](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jsen.md)|
|[`jayschema`](https://github.com/natesilva/jayschema)|[12](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jayschema.md)|
|[`themis`](https://github.com/playlyfe/themis)|[14](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/themis.md)|
|[`schemasaurus`](https://github.com/AlexeyGrishin/schemasaurus)|[16](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/schemasaurus.md)|
|[`jsck`](https://github.com/pandastrike/jsck#readme)|[18](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jsck.md)|
|tv4|[24](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/tv4.md)|
|[`request-validator`](https://github.com/bugventure/request-validator)|[29](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/request-validator.md)|
|[`jassi`](https://github.com/iclanzan/jassi)|[31](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/jassi.md)|
|[`json-model`](https://github.com/geraintluff/json-model)|[40](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/json-model.md)|
|[`JSV`](http://github.com/garycourt/JSV)|[58](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/JSV.md)|
|[`json-gate`](https://github.com/oferei/json-gate)|[72](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/json-gate.md)|
|[`revalidator`](https://github.com/flatiron/revalidator)|[140](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/revalidator.md)|

Some validators have deliberately chosen not to support parts of the spec. Go to the homepage of the validator to learn if
that is the case for these tests.

# Side-effects summary

Number of tests that caused side-effects. The schema or data was altered by the validator.

|Validator|Number of side-effects (BAD)|
|---------|----------------------------|
|tv4|[2](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/tv4-side-effects.md)|
|[`revalidator`](https://github.com/flatiron/revalidator)|[273](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/revalidator-side-effects.md)|
|[`json-model`](https://github.com/geraintluff/json-model)|[294](https://github.com/ebdrup/json-schema-benchmark/blob/master/reports/json-model-side-effects.md)|

Validators not in the list have no side-effects on data or schemas.

# Features of validators

Note that these benchmarks and tests do not take into account other more advanced features of the validators. I encourage
you to take a look at each validator if you are looking for special features.

# Benchmarks by validator authors and others

Several of the validators have build benchmarks themselves. They are
more detailed then the benchmarks provided above.

[Benchmarks owned by themis](https://cdn.rawgit.com/playlyfe/themis/master/benchmark/results.html)

[Benchmarks owned by z-schema](https://rawgit.com/zaggino/z-schema/master/benchmark/results.html)

[Benchmarks owned by jsck](https://github.com/pandastrike/jsck/blob/master/doc/benchmarks.md)

There is also a [benchmark suite](https://github.com/Sembiance/cosmicrealms.com/tree/master/sandbox/benchmark-of-node-dot-js-json-validation-modules-part-3)
by cosmicrealms.

# License
MIT
