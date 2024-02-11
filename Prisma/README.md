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
// getdata
export const GET=async(req,res)=>{
  try{
    const prisma = new PrismaClient()
    const result=await prisma.employee.findMany()
    return NextResponse.json({status:'success',data:result})

  }catch(err){
    console.log(err.toString())
  }
}
```

```js
// data create-Insert one
import { NextResponse } from "next/server"
import { PrismaClient } from '@prisma/client'

export const POST=async(req,res)=>{
  try{
    const jsondata=await req.json()
    const prisma = new PrismaClient()
    let result=await prisma.employee.create({
        data:jsondata
    })
    

    return NextResponse.json({status:'success',data:result})

  }catch(err){
    console.log(err.toString())
  }
}
```
```js
// data create-Insert Many
import { NextResponse } from "next/server"
import { PrismaClient } from '@prisma/client'

export const POST=async(req,res)=>{
  try{
    const jsondata=await req.json()
    const prisma = new PrismaClient()
    let result=await prisma.employee.createMany({
      data:[
        {name:"julfiker1",designation:"student81",city:"India",salary:"44"},
        {name:"julfiker2",designation:"student82",city:"India",salary:"44"},
        {name:"julfiker3",designation:"student83",city:"India",salary:"44"},
      ]
    })
    

    return NextResponse.json({status:'success',data:result})

  }catch(err){
    console.log(err.toString())
  }
}
```

