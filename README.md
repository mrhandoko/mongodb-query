# MongoDB Query

Install first, MongoDB & Mongoose as your databases & ODM.
> npm install mongodb

### Show Databases & Create Databases
> show dbs & use academic

### Create Collection
> db.createCollection("departement", {autoIndexId:true}) or db.createCollection("departement")

### Show List Collections
> db.getCollectionNames or show collections

### Insert Data into Collections
> db.departement.insert({"code":"N001", name: "Manajemen Akuntansi", major : "Ekonomi"})

### Show Data Collection
> db.departement.find() or db.departement.find({})

### Update Data Collection
> db.departement.update({name: "Ekonomi Mikro"},{"$set":{"code":"N003"}})

### Show Collections Schema
> var schema = db.departement.findOne();
> for (var key in schema) { print (key) }


### Seeding data student
> db.student.insert({studentId : 120002, name: "Daniel Sidabutar", address: "Sipiongot", departement: {"code":"T001", name: "Teknik Informatika", major : "Ilmu Komputer"}})

> db.student.insert({studentId : 120003, name: "Diky Arga", address: "Semarang", departement: {"code":"T001", name: "Teknik Informatika", major : "Ilmu Komputer"}})

> db.student.insert({studentId : 120004, name: "Ratna Mauli Santri", address: "Medan", departement: {"code":"N004", name: "Ekonomi Syariah", major : "Ekonomi"}})

> db.student.insert({studentId : 120005, name: "Irwin Sanjaya", address: "Meulaboh", departement: {"code":"T001", name: "Teknik Informatika", major : "Ilmu Komputer"}})

### Insert Reference to Student Collection
> db.student.update({studentId: 120001},{"$set":{"name":"Bambang Handoko", "address":"Medan", "departement":{"$ref":"departement", "$id":ObjectId("58b64ae553976a4ee8f30fd4"),"$db":"academic"}}})

### Show Key name & address in student Collection
> db.student.find({},{_id:0,name:1, address:1})

### Delete all rows
> db.books.remove({})
