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
