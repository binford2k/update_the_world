<!SLIDE >

![Extended again](/_images/python_death_extended.png)


~~~SECTION:notes~~~

* Even with a 12 year offramp, the end still came abruptly.
* Four month reprieve. Again.
* This brand new Mac I'm running, with the latest operating system still defaults to python 2.7
* So does Debian stable.
* So does CentOS
* ...

~~~ENDSECTION~~~


<!SLIDE huge>
# Let's update that clock...

### 🤷‍♀️


<div id="delayed" class="python-27-clock"></div>
<div class="guido-button-block">
    <button class="js-guido-mode guido-button">Enable Guido Mode</button>
</div>

<script>
    $(document).ready(function () {
        var death = moment("20200430", "YYYYMMDD").utc().toDate();
        $('.python-27-clock#delayed').countdown({
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
