<!SLIDE huge>
# Updating the whole world to a new API
## otherwise known as *"eh. I'll get to it"*

### 🤷‍♀️

<div id="original" class="python-27-clock"></div>
<div class="guido-button-block">
    <button class="js-guido-mode guido-button">Enable Guido Mode</button>
</div>

<script>
    $(document).ready(function () {
        var death = moment("20200101", "YYYYMMDD").utc().toDate();
        $('.python-27-clock#original').countdown({
            until: death,
            format: 'YODHMS'
        });
        $('.js-guido-mode').on('click', function () {
            $('.python-27-clock').css({
                "font-family": "'Electrolize', sans-serif",
                "background-color": "black",
                "color": "red"
            });
        });
    });
</script>
<link href='https://fonts.googleapis.com/css?family=Electrolize' rel='stylesheet' type='text/css'>

~~~SECTION:notes~~~

* Does anyone recognize this counter?
* It's the python 2.7 end of life counter.
* It was finally retired for good on new year, 2020.

~~~ENDSECTION~~~
