<!SLIDE center huge>
# Anyone recognize this counter?
### 🐍

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
* And as you can see, it's expired.

~~~ENDSECTION~~~


<!SLIDE >
# Python 2.7 has finally been retired
## Long overdue

    @@@ Python
    #! /usr/bin/env python

    print ('Hello World!')


* January 1994: Python 1.0 meets the world
* October 2000: 2.0 release
* December 2008: 3.0 release

## 2015: Python 2.0 sunset

~~~SECTION:notes~~~

* That's a SEVEN YEAR sunset plan.

~~~ENDSECTION~~~


<!SLIDE >
# Python 2.7 has finally been retired
## Long overdue

    @@@ Python
    #! /usr/bin/env python

    print ('Hello World!')


* January 1994: Python 1.0 meets the world
* October 2000: 2.0 release
* December 2008: 3.0 release

.callout.quote We did not want to hurt the people using Python 2. So, in 2008,
we announced that we would sunset Python 2 in 2015, and asked people to upgrade
before then. Some did, but many did not. So, in 2014, we extended that sunset
till 2020.

## Postponed sunset date of *January 1, 2020*

~~~SECTION:notes~~~

* From the release of 3.0 to the ultimate retiring of the legacy 2.0 line is TWELVE YEARS.

~~~ENDSECTION~~~
