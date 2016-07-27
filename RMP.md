# Resource Management Platform

The Resource Management Platform (RMP) runs on port 1337.
After installing it, you can verify if it is running when you visit

> http://$SERVER:1337/

``$SERVER`` should be replaced with the URL or IP of the server, e.g. localhost.

The site should look like this:

![RMP start screen](screenshots/RMP_start.png)

## Adding a sensor

To add a sensor to the RMP, you have to enter the values of the sensor in the corresponding fields.

|Field         |Meaning                                                   |
|---|---|
|ObjectID      |The name thing that is associated with the sensor         |
|SensorID      |The name of the sensor                                    |
|SensorType    |The type of the sensor, like light sensor                 |
|Sensor URL    |The URL of the sensor. Only important for watchdog sensors|
|Sensor Quality|The quality of how precise the sensor is                  |
|Sensor Unit   |The unit of the sensor, like meters                       |
|Unit Symbol   |The symbol the unit uses, like m                          |
|default value |Value that is returned until a new real value is obtained |

## Endpoints

Path elements preceded by ``:`` are variable names

|Method|Path|Description|
|---|---|---|
|GET|/rmp/sensordata/:thingName/:sensorName|returns the value of the sensor|
|POST|/value|sets the value of the sensor specified in the body|
|GET|/sensor|returns a list of all sensors|
|GET|/sensor/:thingName/:sensorName|returns the specified sensor|
|POST|/sensor|creates a new sensor|
|PUT|/sensor/:thingName/:sensorName|Updates the specified sensor|
|DELETE|/sensor/:thingName/:sensorName|Deletes the specified sensor|

### Examples

![GET /rmp/sensordata/:thingName/:sensorName](screenshots/RMP_getValue.png)

![GET /sensor/:thingName/:sensorName](screenshots/RMP_getValue.png)
