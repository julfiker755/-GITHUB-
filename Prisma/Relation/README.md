// one to one Relation
```js
model users{
  id Int @id @default(autoincrement())
  email String @unique
  password String
  profile profile?
}

model profile {
  id Int @id @default(autoincrement())
  fastname String
  lastname String
  city String
  phonenumber String
  Userid Int @unique
  Users users @relation(fields: [Userid],references: [id],onDelete: Restrict,onUpdate: Cascade)
}
```
