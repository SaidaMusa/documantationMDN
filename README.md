## getCurrentPosition() is a method which can be found device’s current 
location works with HTTPS websites 
If it is not working at all may be it is blocked by geolocation 
### Permissions-Policy. 
### getCurrentPosition(success) 
### getCurrentPosition(success, error) 
### getCurrentPosition(success, error, options) 
### success 
A callback function that takes a GeolocationPosition object as its sole input parameter. 
error Optional 
An optional callback function that takes a GeolocationPositionError object as its sole 
input parameter. 
options Optional 
### maximumAge 
This is also a good method we can predict device’s milestones, if it is maximumAge 0 ,it asks new location gps all 
the time.If it is more than 0 it will ask only that period for example 5(5000 milesstones) and after that period it will 
give you old gps.if its value is infinity it gives you only older gps locations. 
### Timeout – it is like infinity it gives old location 
### EnableHighAccuracy- it is boolean if it is true it can give you possible locations 

![alt text]({BDDC30D2-0CE4-45F2-B954-909D431C752C}.png)



### watchPosition() method

It is available since 2015 July.That is a handler function which finds eachtime user changes location . We can also error handle with it. We can handle it by ID.It has options,error,success just like getCurrentPosition() function.


let id;
let target;
let options;

function success(pos) {
  const crd = pos.coords;

  if (target.latitude === crd.latitude && target.longitude === crd.longitude) {
    console.log("Congratulations, you reached the target");
    navigator.geolocation.clearWatch(id);
  }
}

function error(err) {
  console.error(`ERROR(${err.code}): ${err.message}`);
}

target = {
  latitude: 0,
  longitude: 0,
};

options = {
  enableHighAccuracy: false,
  timeout: 5000,
  maximumAge: 0,
};

id = navigator.geolocation.watchPosition(success, error, options);



### Interfaces

### Geolocation

It is main class of this API. 

### GeolocationPosition

Represents location of a user.A succesfull call  of method in Geolocation.inside a success callback, and contains a timestamp plus a GeolocationCoordinates object instance.


### GeolocationPositionError

A GeolocationPositionError is returned by an unsuccessful call to one of the methods contained inside Geolocation, inside an error callback, and contains an error code and message.




