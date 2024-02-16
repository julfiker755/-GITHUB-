
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

```js
export const POST =async(req,res)=>{
    try{
        const jsondata=await req.json()
        const client=new PrismaClient()
        const result=await client.users.create({
            data:{
                email:"Julfiker7557.bd@gmail.com",
                password:"123456789",
                profile:{
                    create:{
                        fastname:"Julfiker",
                        lastname:"Islam",
                        city:"Bangladesh",
                        phonenumber:"01441703755"
                    }
                },
                post:{
                 create:{
                    title:"Hello world",
                    discripation:"amer soner bangla ami two amy vlo basi"
                 }
                }
            }
        })
        return NextResponse.json({status:'success',data:result})

    }catch(err){
        return NextResponse.json({status:'fail',message:err.toString()})
    }
}
```
```js
export const GET = async (req, res) => {
    try {
        const client = new PrismaClient();
        const result = await client.users.findMany({
            // where:{email:{contains:"Julfiker755.bd@gmail.com"}},
            include:{profile:true,post:true,comment:true}
        })
        return NextResponse.json({ status: 'success', data: result });
    } catch (err) {
        return NextResponse.json({ status: 'fail', message: err.toString() });
    }
};

// example anathor
  const result = await client.users.findMany({
            include:{profile:true,post:{
                where:{title:{contains:"Hello"}},
            },comment:true}
        })
```
