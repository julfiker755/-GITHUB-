<p>
 <h1 style="color:red;" align="center">Prisma Mysql</h1>
</p>

```js
 1. prisma Liser[Link](https://prismaliser.app/)
```

```js
npm install prisma --save-dev
```
```js
npx prisma init --datasource-provider sqlit
npx prisma init --datasource-provider mysql
```

```js
npx prisma migrate dev --name init
```

```js
model employee{
  id Int @id @default(autoincrement())
  name String
  designation String
  city String
  salary String
}

```

```js
// getdata
import { NextResponse } from "next/server"
import { PrismaClient } from '@prisma/client'

export const GET=async(req,res)=>{
  try{
    const prisma = new PrismaClient()
    const result=await prisma.employee.findMany()
    return NextResponse.json({status:'success',data:result})

  }catch(err){
    console.log(err.toString())
  }
}

// extra example
// whare
 const result=await client.employee.findMany({
            where:{name:'xx'}
        })
// select
const result=await client.employee.findMany({
            select:{id:true,name:true,city:false}
        })
// whare and select
const result=await client.employee.findMany({
            where:{name:'julfiker'},
            select:{id:true,name:true,city:false}
        })
// contains [search data selct the fetch]
 const result=await client.employee.findMany({
            where:{name:{contains:"xx"}}
        })
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
```js
// update data
export const POST=async(req,res)=>{
    try{
        const {searchParams}=new URL(req.url)
        const idvalue=searchParams.get("id")
        const id=Number(idvalue)
        const jsondata=await req.json()

        const client=new PrismaClient()
        const result=await client.employee.update({
            where:{id:id},
            data:jsondata
        })

        return NextResponse.json({status:'success',data:result})

    }catch(err){
        return NextResponse.json({status:'fail',message:err.toString()})
    }
}
```

```js
// delete data
export const DELETE=async(req,res)=>{
    try{
        const {searchParams}=new URL(req.url)
        const idvalue=searchParams.get("id")
        const id=Number(idvalue)

        const client=new PrismaClient()
        const result=await client.employee.delete({
            where:{id:id},
        })

        return NextResponse.json({status:'success',data:result})

    }catch(err){
        return NextResponse.json({status:'fail',message:err.toString()})
    }
}
```

