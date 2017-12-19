# It's <span id="demo">Display the result here.</span> and this is my first website.
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.19.3/moment.min.js"></script>
<script>
document.getElementById("demo").innerHTML = moment().format("dddd, MMMM Do YYYY [at] h:mm a");
$.ajax({
  url: "https://api.wunderground.com/api/c7565b96782d982e/conditions/q/MO/Saint_Louis.json",
  success: function( result ) {
    $( "#weather-temp" ).html( "<strong>" + result.current_observation.weather.temp_f + "</strong> degrees" );
  }
});
</script>
The current weather in Saint Louis is <span id="weather-temp">Display the result here.</span>

Thanks to Steven and Greg for teaching the magic

## Feels life changing...opening up a whole new world.

![USA by night](https://svs.gsfc.nasa.gov/vis/a000000/a004000/a004019/E_W_north_america.0001.jpg)

* To see my very first effort go [here](page2.html).

* [Here's what they taught me](howto.html) about using **Atom** and the **command line.**

* And for an explanation of how to add content using only **GitHub pages** go *[here](page3.html)*.

* I even added a special page for [Tech Randy](techrandy.html).

* Greg then taught me how to [add dynamic content](dynamicfeature.html) to an otherwise static website and how to [use an API](addapi.html) to pull data into the website.

It's still all very mysterious but nothing quite like...

![cat eclipse viewing](IMG_0528.JPG)
