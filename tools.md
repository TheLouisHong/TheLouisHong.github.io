---
layout: about
title: Useful Tools by Louis
permalink: /tools/
---

<meta property="og:title" content="Calculate When To Sleep" />
<meta property="og:desciption" content="Need to wake up? When should you sleep to get enough sleep? Try this." />


<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery-timepicker/1.10.0/jquery.timepicker.min.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/jquery-timepicker/1.10.0/jquery.timepicker.min.css">


<h1>Sleep Time Calculator</h1>
<p id="current-time" ></p>

<p>
How much do you want to sleep:

<p>
<input id='ideal-sleep-time' value='8' class="time ui-timepicker-input" type="text" autocomplete="off" onchange='updateSleepTime()'>
 Hours
</p>

</p>

<p>

<p>
When do you need to take up:
</p>

<input id='wake-time' value='10:00am' class="time ui-timepicker-input" type="text" autocomplete="off" onchange='updateSleepTime()'>

<p>

<p>
You should sleep at:
</p>
<h1 id='sleep-time'>
</h1>


</p>

<script type="text/javascript">

    updateSleepTime();

    $('#wake-time').timepicker();
    $('#basicExample').timepicker();

    var date = new Date();
    $('#current-time').text("Time right now: " + formatAMPM(date));

    function formatAMPM(date) {
        var hours = date.getHours();
        var minutes = date.getMinutes();
        var ampm = hours >= 12 ? 'pm' : 'am';
        hours = hours % 12;
        hours = hours ? hours : 12; // the hour '0' should be '12'
        minutes = minutes < 10 ? '0'+minutes : minutes;
        var strTime = hours + ':' + minutes + ' ' + ampm;
        return strTime;
    }

    function updateSleepTime()
    {
        var now = new Date();

        var wake_time = $('#wake-time').val().match(/(\d+)(?::(\d\d))?\s*(p?)/);
        var ideal_sleep_hours = parseInt($('#ideal-sleep-time').val())

        var wake_time_date = new Date();
        wake_time_date.setHours( parseInt(wake_time[1]) + (wake_time[3] ? 12 : 0) );
        wake_time_date.setMinutes( parseInt(wake_time[2]) || 0 );

        var good_hours_of_sleep = ideal_sleep_hours*60*60*1000;
        var sleep_time = new Date(wake_time_date.getTime() - good_hours_of_sleep);
        $('#sleep-time').text(formatAMPM(sleep_time));
    }

</script>

