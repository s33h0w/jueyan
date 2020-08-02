# Migration `20200713103418-init`

This migration has been generated by s33h0w at 7/13/2020, 10:34:18 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE `jueyan`.`user` (
`email` varchar(191) NOT NULL  ,`id` int NOT NULL  AUTO_INCREMENT,`name` varchar(191)   ,
    PRIMARY KEY (`id`)
) DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci

CREATE UNIQUE INDEX `user.email` ON `jueyan`.`user`(`email`)

DROP TABLE `jueyan`.`_migration`;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200713103418-init
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,14 @@
+generator client {
+  provider = "prisma-client-js"
+}
+
+datasource db {
+  provider = "mysql"
+  url      = env("DATABASE_URL")
+}
+
+model user {
+  email String  @unique
+  id    Int     @default(autoincrement()) @id
+  name  String?
+}
```

