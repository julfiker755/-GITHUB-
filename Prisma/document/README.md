```js
export const GET = async (req, res) => {
    try {
        const client = new PrismaClient();
        const result = await client.employee.aggregate({
            _count:{id:true},
            _sum:{salary:true},
            _avg:{salary:true},
            _min:{salary:true},
            _max:{salary:true}
        })
        return NextResponse.json({ status: 'success', data: result });
    } catch (err) {
        return NextResponse.json({ status: 'fail', message: err.toString() });
    }
};

// extra example
 const result = await client.employee.groupBy({
            by:['city'],
            _count:{id:true},
            _sum:{salary:true},
            _avg:{salary:true},
            _min:{salary:true},
            _max:{salary:true}
        })

```

```js
// pagination
export const GET = async (req, res) => {
    try {
        const client = new PrismaClient();
        const result = await client.employee.findMany({
            cursor:{id:5},
            take:3
        })
        return NextResponse.json({ status: 'success', data: result });
    } catch (err) {
        return NextResponse.json({ status: 'fail', message: err.toString() });
    }
};

export const GET = async (req, res) => {
    try {
        const client = new PrismaClient();
        const result = await client.employee.findMany({
            skip:4,
            take:3
        })
        return NextResponse.json({ status: 'success', data: result });
    } catch (err) {
        return NextResponse.json({ status: 'fail', message: err.toString() });
    }
};
```

```js
//  Time Calculation And Logging
export const GET = async (req, res) => {
    try {
        const client = new PrismaClient({log:['query','info','warn','error']});
        const starTime=Date.now()
        const result = await client.employee.findMany()
        const exeTime=(Date.now() - starTime) + " miliseconds"
        return NextResponse.json({time:exeTime, status: 'success', data: result });
    } catch (err) {
        return NextResponse.json({ status: 'fail', message: err.toString() });
    }
};

```
```js
```