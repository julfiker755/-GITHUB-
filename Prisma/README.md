<p>
 <h1 style="color:red;" align="center">Prisma Mysql</h1>
</p>


```js
npm install prisma --save-dev
```
```js
npx prisma init --datasource-provider sqlit
npx prisma init --datasource-provider mysql
```
```js
model User {
  id    Int     @id @default(autoincrement())
  email String  @unique
  name  String?
  name  String
}
```
```js
npx prisma migrate dev --name init
```

```js
// Prisma Numbers Type
```
