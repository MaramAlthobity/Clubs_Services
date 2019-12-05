## The Backend
The backend is hosted on [https://clubservices.herokuapp.com/api/v1](https://clubservices.herokuapp.com/api/v1)

### API Endpoints
The following are the API endpoints used to access the different resources on the backend.
You can use [Postman](https://www.getpostman.com/) or any other API browsing tool to access these endpoints.

All Endpoints must be prefixed with the API host url [https://clubservices.herokuapp.com/api/v1](https://clubservices.herokuapp.com/api/v1)

#### Signup
`POST /api/v1/register`

```json
{
	"name": "Full Name",
	"email": "someone@gmail.com",
	"phoneNumber": "1297981322",
	"password": "password"
}
```
Response 
```json
{
    "success": true,
    "message": "Login successful",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiRnVsbCBOYW1lIiwiZW1haWwiOiJzb21lb25lQGdtYWlsLmNvbSIsInBob25lTnVtYmVyIjoiMTI5Nzk4MTMyMiIsImdlbmRlciI6bnVsbCwidHlwZSI6InVzZXIiLCJpYXQiOjE1NTI0MTAzMzIsImV4cCI6MTU1MzAxNTEzMn0.vxM9trvVhUJVgK43DkUbZGw4ASI3UksRIvDeNUNPiTE",
    "user": {
        "id": 1,
        "name": "Full Name",
        "email": "someone@gmail.com",
        "phoneNumber": "1297981322",
        "gender": null,
        "createdAt": "2019-03-02T08:29:41.658Z",
        "updatedAt": "2019-03-02T08:29:41.658Z"
    }
}
```

#### Login
`POST /api/v1/login`
```json
{
	"email": "someone@gmail.com",
	"password": "password"
}
```
Response
```json
{
    "success": true,
    "message": "Login successful",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiRnVsbCBOYW1lIiwiZW1haWwiOiJzb21lb25lQGdtYWlsLmNvbSIsInBob25lTnVtYmVyIjoiMTI5Nzk4MTMyMiIsImdlbmRlciI6bnVsbCwidHlwZSI6InVzZXIiLCJpYXQiOjE1NTI0MTAzMzIsImV4cCI6MTU1MzAxNTEzMn0.vxM9trvVhUJVgK43DkUbZGw4ASI3UksRIvDeNUNPiTE",
    "user": {
        "id": 1,
        "name": "Full Name",
        "email": "someone@gmail.com",
        "phoneNumber": "1297981322",
        "gender": null,
        "createdAt": "2019-03-02T08:29:41.658Z",
        "updatedAt": "2019-03-02T08:29:41.658Z"
    }
}
```

### Get Clubs
`GET /api/v1/clubs`
```json
{
    "success": true,
    "message": "Clubs retrieved successfully",
    "clubs": [
        {
            "id": 1,
            "name": "Fitness Time Club",
            "image": "https://www.firmdalehotels.com/media/1036949/crosby-street-hotel-gym.jpg?a=1&anchor=center&mode=crop&width=798&height=544&bgcolor=fff",
            "phoneNumber": "1798712698723",
            "email": "fitnessclub@gmail.com",
            "location": "Taif",
            "time": "Open 12:00 Closes 16:00",
            "menFees": 300,
            "womenFees": 200,
            "childFees": 100,
            "gender": "Female",
            "createdAt": "2019-03-01T21:25:16.827Z",
            "updatedAt": "2019-03-01T22:03:19.640Z"
        },
        {
            "id": 2,
            "name": "Health Club",
            "image": "https://media.wmagazine.com/photos/5853339ac7188f9b26c915ea/3:2/w_640/Dogpound_Group-Workout-2.jpg",
            "phoneNumber": "123698123",
            "email": "healthclub@gmail.com",
            "location": "Jeddah",
            "time": "Open 08:00 Closes 16:00",
            "menFees": 500,
            "womenFees": 400,
            "childFees": 100,
            "gender": "Male",
            "createdAt": "2019-03-01T21:25:16.827Z",
            "updatedAt": "2019-03-01T22:03:19.640Z"
        }
    ]
}
```

### Update User Profile
`PUT /api/v1/user`
```json
{
	"name": "Full Names",
	"email": "someone@gmail.com",
	"phoneNumber": "1297981323",
	"gender": "Male"
}
```
Response
```json
{
    "success": true,
    "message": "User information updated successfully",
    "user": {
        "id": 1,
        "name": "Full Names",
        "email": "someone@gmail.com",
        "phoneNumber": "1297981323",
        "gender": "Male",
        "createdAt": "2019-03-02T08:29:41.658Z",
        "updatedAt": "2019-03-12T17:08:21.613Z"
    }
}
```
### Make Reservation
`POST /api/v1/club/<club_id>/reserve`
```json
{
	"startDate": "03/04/2019 16:00",
	"endDate": "03/04/2019 17:00"
}
```

### Get Reservations
`GET /api/v1/reservations`
```json
{
    "success": true,
    "message": "Reservations fetched successfully",
    "reservations": [
        {
            "id": 1,
            "startDate": "2019-03-04T09:00:00.000Z",
            "endDate": "2019-03-04T10:00:00.000Z",
            "createdAt": "2019-03-03T04:27:46.148Z",
            "updatedAt": "2019-03-03T04:27:46.148Z",
            "club": {
                "id": 1,
                "name": "Fitness Time Club",
                "image": "https://www.firmdalehotels.com/media/1036949/crosby-street-hotel-gym.jpg?a=1&anchor=center&mode=crop&width=798&height=544&bgcolor=fff",
                "phoneNumber": "1798712698723",
                "email": "fitnessclub@gmail.com",
                "location": "Taif",
                "time": "Open 12:00 Closes 16:00",
                "menFees": 300,
                "womenFees": 200,
                "childFees": 100,
                "gender": "Female",
                "createdAt": "2019-03-01T21:25:16.827Z",
                "updatedAt": "2019-03-01T22:03:19.640Z"
            }
        },
        {
            "id": 2,
            "startDate": "2019-03-04T09:00:00.000Z",
            "endDate": "2019-03-04T10:00:00.000Z",
            "createdAt": "2019-03-03T04:30:46.417Z",
            "updatedAt": "2019-03-03T04:30:46.417Z",
            "club": {
                "id": 1,
                "name": "Fitness Time Club",
                "image": "https://www.firmdalehotels.com/media/1036949/crosby-street-hotel-gym.jpg?a=1&anchor=center&mode=crop&width=798&height=544&bgcolor=fff",
                "phoneNumber": "1798712698723",
                "email": "fitnessclub@gmail.com",
                "location": "Taif",
                "time": "Open 12:00 Closes 16:00",
                "menFees": 300,
                "womenFees": 200,
                "childFees": 100,
                "gender": "Female",
                "createdAt": "2019-03-01T21:25:16.827Z",
                "updatedAt": "2019-03-01T22:03:19.640Z"
            }
        }
    ]
}
```

### Search Clubs
`GET /api/v1/clubs`

Query Params
```json
{
  "minFees": 1200,
  "maxFees": 1300,
  "services": "Laundry, Other",
  "equipment": "Hammer, Basket",
  "gender": "Male"
}
```

### Get Workouts
`GET /api/v1/workouts`
```json
{
    "success": true,
    "message": "Workouts retrieved successfully",
    "workouts": [
        {
            "id": 1,
            "name": "Super-Pump Arm Workout",
            "video": "https://www.youtube.com/watch?v=S5kOK3bxfro",
            "image": "",
            "createdAt": "2019-03-01T21:25:16.827Z",
            "updatedAt": "2019-03-01T22:03:19.640Z"
        },
        {
            "id": 2,
            "name": "Leg Workouts",
            "video": "https://www.youtube.com/watch?v=8yLnrF_Ar-",
            "image": "http://www.workoutbox.net/wp-content/uploads/2018/06/5-legs-workout-at-gym--1024x700.png",
            "createdAt": "2019-03-01T21:25:16.827Z",
            "updatedAt": "2019-03-01T22:03:19.640Z"
        }
    ]
}
```