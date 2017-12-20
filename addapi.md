# Using an API presented another challenge.
* First, it requires deciding what data set to include.  There are lots of choices, including:
  * [Data.gov](https://www.data.gov/) which has lots of government data and APIs to provide easy access;
  * Gray Brooks [API-mashup](https://github.com/gbinal/api-mashup);
  * [ProgramableWeb](https://www.programmableweb.com/category/all/apis);
or the one I finally settled on
  * [Weather Underground](https://www.wunderground.com/weather/api/d/docs).

  Getting started with Weather Underground required:

    1. Signing up for their "API key"
    2. Deciding which of the many data features to include; and
    3. Finding some reusable javascript (remember I don't know how to code!) to make it happen.

To find reusable code for this Greg suggested a Google search for "Ajax js library".  I'm still not sure why but he suggested Using [JQuery.com](https://jquery.com/) which appears to have an easy to use Ajax library already set up with a weather script.

It looks like this:

```
Ajax
Call a local script on the server /api/getWeather with the query parameter zipcode=97201 and replace the element #weather-temp's html with the returned text.

$.ajax({
  url: "/api/getWeather",
  data: {
    zipcode: 97201
  },
  success: function( result ) {
    $( "#weather-temp" ).html( "<strong>" + result + "</strong> degrees" );
  }
});
```

The next step required adding the Jquery code to my GitHub index.md page. Greg says Jquery script needs to come before other scripts so I added it inside my <script> but before the cloudflare script I used to add the time and date element.

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
```

Next, I swapped out the "relative url" (meaning it only goes to a url on my server not to an https url like wunderground)

```
url: "/api/getWeather",
  data: {
    zipcode: 97201
  },
  ```

with the Weather Underground url (and adding variables in order to properly display both the weather and temperature).

```
$.ajax({
  url: "https://api.wunderground.com/api/c7565b96782d982e/conditions/q/MO/Saint_Louis.json",
  success: function( result ) {
    var weather=result.current_observation.weather;
    var temp_f=result.current_observation.temp_f
    $( "#weather-temp" ).html( "<strong>" + weather + " and " + temp_f + "</strong> degrees" ).;
  }
});
</script>
```
