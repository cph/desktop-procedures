# [Developing Features](../developing_features.md) / Automated Tests


#### Rationale

Automated tests have costs and benefits.

###### Benefits of writing a test

1. It can protect against regressions
2. It can document the developer's intention
3. It can inspire confidence (that a feature is working, that a refactor is safe)

###### Costs of writing a test

1. It takes time to write
2. It takes time to maintain
3. It takes time to run

###### Conclusions

- A developer should write tests when the benefits outweigh the costs.
- A developer should write tests to maximize their benefits and minimize their costs.


#### General Rules

- Prefer unit tests to integration tests and integration tests to acceptance tests (unit tests cost less to run and maintain)
- Write tests around code:
   - where bugs are more costly (e.g. permissions, deletes/updates, signin/signup)
   - where bugs are harder to observe (e.g. lower-level logic)
   - with complex requirements (in order to describe the requirements)
- Write failing tests before starting a feature or fix (the test will influence how you design the code, making the code easier test, and the test cheaper to maintain)


#### Related Topics

- [Testing 101: Structural Patterns](https://vimeo.com/218208271) — see this video for examples of how to write more maintainable tests.
