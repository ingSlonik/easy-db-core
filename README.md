# Easy DB Core

Core of Lite&easy database for the same interface of any implementation.
The same interface can be used in Node, Web, Mobile, Server and Develop applications.

## API interface

```js
import { insert, select, update, remove } from "easy-db-*";

// INSERT
const idOfRow = await insert("collection1", { myRow: 1 });

// SELECT
const allCollection1 = await select("collection1");
const myRow1 = await select("collection1", idOfRow);

// UPDATE
await update("collection1", idOfRow, { ...myRow1, update: 1 });

// DELETE
await remove("collection1", idOfRow); // only one row
```

## Your implementation for this interface

```js
import easyDBCore from "easy-db-core";

type Data = { [id: number | string]: any };

export default const easyDBInstance = easyDBCore({
    async saveCollection(name: string, data: Data) {
        // code for save collection
    },
    async loadCollection(name: string): Promise<null | Data> {
        // code for load collection
    },
});
```
