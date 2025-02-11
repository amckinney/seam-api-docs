# Update Climate Setting Schedule

{% swagger method="post" path="/climate_setting_schedules/update" baseUrl="https://connect.getseam.com" summary="Updating a Climate Setting Schedule" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="climate_setting_schedule_id" %}
ID of the Climate Setting Schedule
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="false" %}
Name of the Access Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="schedule_starts_at" required="false" type="ISO8601 string" %}
Start Time of the Climate Setting Schedule
{% endswagger-parameter %}

{% swagger-parameter in="body" name="schedule_ends_at" required="false" type="ISO8601 string" %}
End Time of the Climate Setting Schedule
{% endswagger-parameter %}

{% swagger-parameter in="body" name="automatic_heating_enabled" required="false" type="boolean" %}
Default: false

\


When enabled, your system will only heat your home. Your thermostat will start heating to maintain the heating set point temperature selected.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="automatic_cooling_enabled" required="false" type="boolean" %}
Default: false

\


When enabled, your system will only cooling your home. Your thermostat will start cooling to maintain the cooling set point temperature selected.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <API_KEY>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="heating_set_point_fahrenheit" type="number" %}
When 

`automatic_heating_enabled`

 is set, a heating set point must be provided. The thermostat will start heating to maintain this temperature set point.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cooling_set_point_fahrenheit" type="number" %}
When 

`automatic_cooling_enabled`

 is set, a cooling set point must be provided. The thermostat will start cooling to maintain this temperature set point.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="manual_override_allowed" type="boolean" required="false" %}
Default: false

Whether another user can use the thermostat or API to override this climate setting
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
  "action_attempt": {
    "status": "pending",
    "action_type": "UPDATE_CLIMATE_SETTING_SCHEDULE",
    "action_attempt_id": "c10e3db5-a5a2-47f2-a76f-48379ed9cd22",
    "result": null,
    "error": null
  },
  "climate_setting_schedule": {
    "climate_setting_schedule_id": "123e4567-e89b-12d3-a456-426614174000",
    "device_id": "123e4567-e89b-12d3-a456-426614174001",
    "name": "Guest Stay #1234",
    "schedule_starts_at": "2022-07-01T10:40:00Z",
    "schedule_ends_at": "2022-07-10T10:40:00Z",
    "created_at": "2022-07-06T23:26:42.223Z",
    "is_set_on_device": false,
    "automatic_heating_enabled": true,
    "automatic_cooling_enabled": true,
    "hvac_mode_setting": "heat_cool",
    "cooling_set_point_fahrenheit": 75,
    "heating_set_point_fahrenheit": 65,
    "manual_override_allowed": false
  },
  "ok": true
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "error": {
    "type": "invalid_input",
    "message": "Required for provided \"device_id\"",
    "validation_errors": {
      "_errors": [],
      "device_id": {
        "_errors": [
          "Required"
        ]
      }
    },
    "request_id": "9f3e59f1-cfb5-4e48-93df-0a988554eb0b"
  },
  "ok": false
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
  "error": {
    "type": "device_not_found",
    "message": "Device not found",
    "request_id": "552c8cf1-3dbc-4920-adc6-047328e39369"
  },
  "ok": false
}
```
{% endswagger-response %}
{% endswagger %}

### Code Examples

{% tabs %}
{% tab title="Python" %}
```python
seam.climate_setting_schedules.update(
    "123e4567-e89b-12d3-a456-426614174001",
    automatic_heating_enabled=False,
    heating_set_point_fahrenheit=null,
)

# ClimateSettingSchedule:
#    climate_setting_schedule_id: 123e4567-e89b-12d3-a456-426614174000
#    device_id: 123e4567-e89b-12d3-a456-426614174001
#    name: Guest Stay #1234  
#    schedule_starts_at: 2022-07-01T10:40:00Z    
#    schedule_ends_at: 2022-07-10T10:40:00Z     
#    created_at: 2022-07-06T23:26:42.223Z      
#    is_set_on_device: False
#    automatic_cooling_enabled: True  
#    hvac_mode_setting: cool
#    cooling_set_point_fahrenheit: 75 
#    manual_override_allowed: False

```
{% endtab %}

{% tab title="Javascript" %}
```javascript
await seam.climateSettingSchedules.update({
    climate_setting_schedule_id: "cd706212-ec14-499a-abd5-ba04123ee65e",
    automatic_heating_enabled: false,
    heating_set_point_fahrenheit: null,
});

/*
{
    "climate_setting_schedule_id": "123e4567-e89b-12d3-a456-426614174000",
    "device_id": "123e4567-e89b-12d3-a456-426614174001",
    "name": "Guest Stay #1234",
    "schedule_starts_at": "2022-07-01T10:40:00Z",
    "schedule_ends_at": "2022-07-10T10:40:00Z",
    "created_at": "2022-07-06T23:26:42.223Z",
    "is_set_on_device": false,
    "automatic_heating_enabled": true,
    "hvac_mode_setting": "cool",
    "cooling_set_point_fahrenheit": 75,
    "manual_override_allowed": false
}
*/
```
{% endtab %}
{% endtabs %}

### Parameters

| `name`                         | <p>type: string<br>Optional</p>         | Name of Climate Setting Schedule                                                                                                                         |
| ------------------------------ | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `schedule_starts_at`           | <p>type: ISO8601 string<br>Optional</p> | Date time when the Climate Setting Schedule should be programmed                                                                                         |
| `schedule_ends_at`             | <p>type: ISO8601 string<br>Optional</p> | Date time when the Climate Setting Schedule should be removed                                                                                            |
| `automatic_heating_enabled`    | <p>type: boolean<br>Optional</p>        | When enabled, your system will only heat your home. Your thermostat will start heating to maintain the heating set point temperature selected.           |
| `automatic_cooling_enabled`    | <p>type: string<br>Optional</p>         | When enabled, your system will only cooling your home. Your thermostat will start cooling to maintain the cooling set point temperature selected.        |
| `heating_set_point_fahrenheit` | <p>type: number<br>Optional</p>         | When `automatic_heating_enabled` is set, a heating set point must be provided. The thermostat will start heating to maintain this temperature set point. |
| `cooling_set_point_fahrenheit` | <p>type: number<br>Optional</p>         | When `automatic_cooling_enabled` is set, a cooling set point must be provided. The thermostat will start cooling to maintain this temperature set point. |
| `manual_override_allowed`      | <p>type: boolean<br>Optional</p>        | Whether another user can use the thermostat or API to override this climate setting                                                                      |

###

### Response

This section shows the JSON response returned by the API. Since each language encapsulates this response inside objects specific to that language and/or implementation, the actual type in your language might differ from what’s written here.

#### JSON format

{% tabs %}
{% tab title="JSON" %}
```json
{
  "action_attempt": {
    "status": "pending",
    "action_type": "UPDATE_CLIMATE_SETTING_SCHEDULE",
    "action_attempt_id": "bbb8a07d-a91d-4564-b002-8172f7cdadc4",
    "result": null,
    "error": null
  },
  "ok": true
}
```
{% endtab %}
{% endtabs %}
