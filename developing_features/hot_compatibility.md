# [Developing Features](../developing_features.md) / Hot Compatibility

#### Rationale

Since it's our goal to [deploy frequently](../deploying_changes.md), we especially don't want deploys to adversely affect production (by causing bugs, lags, or downtime).

"Hot Compatibility" is a term coined by Pedro Belo to designate a way of deploying changes (especially database changes) so that the outgoing (running) codebase will run on the incoming (deploying) codebase.

#### Goals

These processes should ensure that:

 1. Code immediately before and after major changes in the application can both still run on the same database.
 2. Database operations do not "lock" the database for an extended period (more than a handful of seconds).
 3. All major changes in an application are thoroughly thought through to have minimal impact on user experience as they're being rolled out.


#### Procedures

 - When **removing** tables, columns, or API endpoints, first ensure that no production code is currently using them.\
 - When **renaming** tables, or **altering** columns or API endpoints, do it in three steps:
    1. Modify the code to write to _both_ the old table/column/endpoint and the new one.
    2. Switch from reading from the old location to the new one.
    3. Remove the old table/column/endpoint and any extra code you'd added for compatibility.

 - When **adding an index** or doing a **long-running migration**, disable the DDL transaction (and do the index concurrently) so that the application is not locked out of those tables.

    ```ruby
    class AddIndexToColumnOnTable < ActiveRecord::Migration
      disable_ddl_transaction!

      def change
        add_index :table, :column, algorithm: :concurrently
      end
    end
    ```

 - When **adding a NOT NULL constraint** to a column:
    1. Ensure the model is writing a default value to the column you wish to constrain.
    2. Update all records with null values in the column to have the default instead.
    3. Add the constraint.

#### References

 - [Rails Migrations with Zero Downtime](http://blog.codeship.com/rails-migrations-zero-downtime/) by Pedro Belo
