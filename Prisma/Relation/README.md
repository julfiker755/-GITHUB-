
```js
model users{
  id Int @id @default(autoincrement())
  email String @unique
  password String
  profile profile?
  post post[]
  commnet comment[]
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

model post {
  id Int @id @default(autoincrement())
  title String
  discripation String @db.LongText
  userID Int
  user users @relation(fields: [userID],references: [id],onDelete: Restrict,onUpdate: Cascade)
  comment comment[]
}

model comment{
  id Int @id @default(autoincrement())
  text String
  userid Int
  user users @relation(fields: [userid],references: [id],onDelete: Restrict,onUpdate: Cascade)
  postId Int
  post post @relation(fields: [postId],references: [id],onDelete: Restrict,onUpdate: Cascade)
}
```
