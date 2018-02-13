# sway-resolve-reference

Illustrating an issue with [Sway](https://github.com/apigee-127/sway) and circular references.

See https://github.com/apigee-127/sway/issues/165


To reproduce:

```
git clone git@github.com:penx/sway-resolve-reference.git
cd sway-resolve-reference
npm run debug
```

Then, with the mock server running:

```
npm test
```

Uses openapi-mock, that uses a GitHub fork of [swagger-node-runner](https://github.com/penx/swagger-node-runner/tree/feature/support-date-in-mocks), that uses a [GitHub fork of Sway](https://github.com/penx/sway/tree/feature/date-format-in-mocks), which uses json-refs@3.0.4.

```
sway-resolve-reference@0.0.1
└─┬ openapi-mock@0.0.4
  └─┬ swagger-node-runner@0.7.3 (github:penx/swagger-node-runner#b73eb1c5c7bbdae207957692f0f9d8379ba84866)
    └─┬ sway@1.0.0 (github:penx/sway#8ebcbf84dcaf7ab38ed6830e43cd3f36b6912aec)
      └── json-refs@3.0.4
```
