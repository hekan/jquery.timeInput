#About
**jQuery timeInput** is a time picker plugin for jQuery based on the HTML5 spec, but it's backwards compatible with older browsers. Just a simple dropdown with suggested times in 24h format. The HTML5 spec doesn't allow am/pm or localized time syntax, so it only allowes the format hh:mm. Seconds is allowed according to spec, but I have not implemented it yet. Validates and corrects input. Feel free to send me pull requests.

Inspired by the jQuery timePicker plugin:

 - [Sam Collet](http://www.texotela.co.uk)
 - [Anders Fajerson](http://perifer.se)

The syntax is as follows:

    <input type="time" name="myTime" class="time-mm-hh" min="9:00" max="18:00" step="1800" />
    <input type="time" name="myTime2" class="time-mm-hh" />

    <script type="text/javascript">
        $("input[name='myTime']").timeInput(); // use default or html5 attributes
        $("input[name='myTime2']").timeInput({min: "6:00", max: "15:00", step: 900}); // 15 min intervals from 6:00 am to 3:00 pm
    </script>


## jQuery Compatibility

Works with jQuery 1.4.2 and newer. (uses delegate)

Should work with:

 - IE 6/7/8
 - FF
 - Opera
 - Safari
 - Chrome

## Notes

Validates input like this:

 - Insert ":" if missing
 - Not valid time? Replace with blank
 - Not a valid time according to step? Round up/down to closest step

IE won't let you use the selector input[type=time]. So use a class or similar instead.

Opera doesn't allow you to prevent the default action for keyboard events, so it's not possible to do custom handling of the arrow keys. This causes the direction to be opposite in Opera than in other browsers.
