# ERD 
![dbdiagram](/uploads/a404961f0e6a4c6bf3633860e125b784/dbdiagram.png)

# Car Management Dashboard
![alt text](https://github.com/bayuik/car-management-dashboard/blob/main/ERD/ERD.png)

# Client
1. Halaman Index (GET) = http://localhost/
2. Halaman Create Car (POST) = http://localhost/create-car
3. Halaman Edit Car (GET) = http://localhost/edit-car/:id
4. Menampilkan Hasil Filter (GET) = http://localhost/:id
5. Menampilkan Hasil Search (POST) = http://localhost/search

# API 
1. Create Car (POST) = http://localhost:3000/api/v1/Cars
2. Read All Cars (GET) = http://localhost:3000/api/v1/Cars
3. Read One Car (GET) = http://localhost:3000/api/v1/Cars/:id
4. Update Car (POST) = http://localhost:3000/api/v1/Cars/:id
5. Delele Car (GET) = http://localhost:3000//api/v1/deleteCars/:id
6. Filter Car (GET) = http://localhost:3000/api/v1/FilterCars/:id
7. Search Car (GET) = http://localhost:3000/api/v1/SearchCars/:search


# Endpoint
### Get all cars list
http://localhost:3000/api/v1/Cars

##### Example request Body
```
var config = {
  method: 'get',
  url: 'http://localhost:3000/api/v1/Cars',
  headers: { }
};

```
##### Output examples
```
[
  {
    "id":8,
    "name_car":"Daihatsu",
    "rent_cost":250000,
    "image_car":"image_car-1650624422305.png",
    "id_type":2,
    "createdAt":"2022-04-22T10:47:02.493Z",
    "updatedAt":"2022-04-22T10:47:02.493Z",
    "type_car":null
  },

  {
    "id":5,
    "name_car":"Brio",
    "rent_cost":310000,
    "image_car":"image_car-1650624176685.png",
    "id_type":2,
    "createdAt":"2022-04-22T10:42:56.697Z",
    "updatedAt":"2022-04-22T10:42:56.697Z","type_car":null
  }
]
```

---

### Get car by id
http://localhost:3000/api/v1/Cars/:id


##### Example request body
```
var config = {
  method: 'get',
  url: 'http://localhost:3000/api/v1/Cars/5',
  headers: { }
};

```

##### Output Example
```
{
  "id":5,
  "name_car":"Brio",
  "rent_cost":310000,
  "image_car":"image_car-1650624176685.png",
  "id_type":2,
  "createdAt":"2022-04-22T10:42:56.697Z",
  "updatedAt":"2022-04-22T10:42:56.697Z",
  "type_car":null
}

```
---

### Get car by size
http://localhost:3000/api/v1/FilterCars/:id
##### Example request body
```
var config = {
  method: 'get',
  url: 'http://localhost:3000/api/v1/FilterCars/2',
  headers: { }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```
##### Output Examples
```
[
 {
  "id":5,
  "name_car":"Brio",
  "rent_cost":310000,
  "image_car":"image_car-1650624176685.png",
  "id_type":2,
  "createdAt":"2022-04-22T10:42:56.697Z",
  "updatedAt":"2022-04-22T10:42:56.697Z",
  "type_car":null
 }
]
```
---

### Post car
http://localhost:3000/api/v1/Cars

##### Example request body
```
var data = new FormData();
data.append('name', 'Porsche');
data.append('price', '200000');
data.append('size', 'small');
data.append('image', fs.createReadStream('/C:/Users/bayui/Pictures/242030506_1182991045518652_4803178363987901143_n.jpg'));

var config = {
  method: 'post',
  url: 'http://localhost:3000/api/v1/Cars',
  data : data
};

```
##### Example output
```
{
    "message": "Car created"
}
```
---

### Put car
http://localhost:3000/api/v1/Cars/:id

##### Example request body
```
var data = new FormData();
data.append('name', 'Porsche');
data.append('price', '200000');
data.append('size', 'medium');
data.append('image', fs.createReadStream('/C:/Users/bayui/Pictures/242030506_1182991045518652_4803178363987901143_n.jpg'));

var config = {
  method: 'put',
  url: 'http://localhost:3000/api/v1/Cars/5d',
  headers: { 
    ...data.getHeaders()
  },
  data : data
};

```


##### Example output
```
{
    "message": "Car updated"
}
```

---
### Delete car
http://localhost:3000//api/v1/deleteCars/:id
##### Example request body
```
var config = {
  method: 'delete',
  url: 'http://localhost:3000//api/v1/deleteCars/5',
  headers: { }
};

```

Example Output
```
{
    "message": "Car deleted successfully"
}
```
