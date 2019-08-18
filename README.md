# localorder

A Clojure web application.

## Usage

Test db connection

```
lein repl

(require '[clojure.java.jdbc :as sql])

(sql/db-do-commands "postgres://localhost:5432/d86ob0nd0373ik"
                           (sql/create-table-ddl :testing [[:data :text]]))

(sql/insert! "postgres://localhost:5432/d86ob0nd0373ik"
                    :testing {:data "Hello World"})

(sql/query "postgres://localhost:5432/d86ob0nd0373ik"
                  ["select * from testing"])

(sql/db-do-commands "postgres://localhost:5432/d86ob0nd0373ik"
                           "drop table testing")
```

Init

```
(require 'localorder.core)

(localorder.core/-main)

```

How Html works

```
(require '[hiccup.core :as h])

```

Development

```
lein run -m localorder.core
```

Deployment

```
lein uberjar

```

## License

Copyright © 2019 localorder

This program and the accompanying materials are made available under the
terms of the Eclipse Public License 2.0 which is available at
http://www.eclipse.org/legal/epl-2.0.

This Source Code may also be made available under the following Secondary
Licenses when the conditions for such availability set forth in the Eclipse
Public License, v. 2.0 are satisfied: GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or (at your
option) any later version, with the GNU Classpath Exception which is available
at https://www.gnu.org/software/classpath/license.html.
