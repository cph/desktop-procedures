# [Developing Features](../developing_features.md) / Test-Driven Development

#### Rationale

Automated tests ensure that code works as expected and add safety and confidence to both adding new features and refactoring projects. We always seek to maintain good test coverage and wherever possible develop features by writing tests first. By defining feature behavior at the outset, implementation details remain just that--details that are ultimately unimportant so long as the behavior of the feature remains consistent.

#### Goals

These procedures should ensure:

 - that the behaviors of features are well-defined
 - that regressions introduced by developing or refactoring features are minimized

#### Tools Used

 - [Jenkins](https://ci.cphepdev.com/)

#### Procedures

 - Every class should be covered by unit tests.
 - Especially complex behavior involving several classes (e.g., responding to API requests) should be covered by integration tests.
 - As much of the interface as is feasible should be covered by acceptance tests.
 - When developing a new feature we:
   - Enumerate the required classes' behaviors (public interfaces) _first_.
   - Write failing tests that assert the expected behavior.
   - Code each class so that the tests pass.
   - Refactor the code as necessary to be consistent with our [style guides](https://github.com/cph/style-guides)
 - Only a class' _public_ interface should be covered by automated tests.
