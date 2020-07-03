# Table

Table widget comes handy when you need to structure similar data within 1 graphical element. It works as a usual table.

You can add a row to the table with :

```text
Blynk.virtualWrite(V1, "add", id, "Name", "Value");
```

You can update a row in the table with :

```text
Blynk.virtualWrite(V1, "update", id, "UpdatedName", "UpdatedValue");
```

To highlight any item in a table by using it's id in a table :

```text
Blynk.virtualWrite(V1, "pick", 0);
```

To select/deselect \(make icon green/grey\) item in a table by using it's row id in a table :

```text
Blynk.virtualWrite(V1, "select", 0);
Blynk.virtualWrite(V1, "deselect", 0);
```

To clear the table at any time with:

```text
Blynk.virtualWrite(V1, "clr");
```

You can also handle other actions coming from table. For example, use row as a switch button.

```text
BLYNK_WRITE(V1) {
   String cmd = param[0].asStr();
   if (cmd == "select") {
       //row in table was selected. 
       int rowId = param[1].asInt();
   }
   if (cmd == "deselect") {
       //row in table was deselected. 
       int rowId = param[1].asInt();
   }
   if (cmd == "order") {
       //rows in table where reodered
       int oldRowIndex = param[1].asInt();
       int newRowIndex = param[2].asInt();
   }
}
```

**Note :** Max number of rows in the table is 100. When you reach the limit, table will work as FIFO \(First In First Out\) list. This limit can be changed by configuring `table.rows.pool.size` property for Local Server.

**Sketch:** [Simple Table usage](https://github.com/blynkkk/blynk-library/blob/master/examples/Widgets/Table/Table_Simple/Table_Simple.ino)

**Sketch:** [Advanced Table usage](https://github.com/blynkkk/blynk-library/blob/master/examples/Widgets/Table/Table_Advanced/Table_Advanced.ino)

