# RetainedDateTimePickers
Android Library to help you with your date & time pickers while retaining the instance of the pickers on orientation change.

# Installation

#### Gradle
```groovy
compile 'com.github.k0shk0sh:RetainedDateTimePickers:1.0.0'
```

#### Maven
```xml
<dependency>
  <groupId>com.github.k0shk0sh</groupId>
  <artifactId>RetainedDateTimePickers</artifactId>
  <version>1.0.0</version>
  <type>aar</type>
</dependency>
```

Screenshots 
======
```xml
    <coming soon/>
```

Usage
=====

Your `Activity` or `Fragment` must implement `DatePickerCallback` and or `TimePickerCallback` to receive the selected date & selected time if 
applicable.

RetainedDateTimePickers should be treated as any normal `DialogFragment`:

- DatePickerDialog Only 
```java
DatePickerFragmentDialog.newInstance().show(getSupportFragmentManager(), "DatePickerFragmentDialog");
```

- TimePickerDialog Only
```java
//default  12 hours format
TimePickerFragmentDialog.newInstance().show(getSupportFragmentManager(), "TimePickerFragmentDialog");
//24 hours format
TimePickerFragmentDialog.newInstance(true).show(getSupportFragmentManager(), "TimePickerFragmentDialog");
```

- DateTimePickerDialog 
```java
DatePickerFragmentDialog.newInstance(true).show(getSupportFragmentManager(), "DatePickerFragmentDialog");
```

- Date & Time PickerDialog Customization
```java
DatePickerFragmentDialog.newInstance(
        DateTimeBuilder.get()
                .withTime(true)
                .with24Hours(true)
                .withSelectedDate(currentDate.getTimeInMillis())
                .withMinDate(minDate.getTimeInMillis())
                .withMaxDate(maxDate.getTimeInMillis())
                .withCurrentHour(12)
                .withCurrentMinute(30)
                .withTheme(R.style.PickersTheme))
        .show(getSupportFragmentManager(), "DatePickerFragmentDialog");
```


> **To understand more how the library works, please take a look at the sample app.**


TODO
=====

- ~~To supports `ParentFragment` (very soon).~~

# Why this library?

* DatePickerDialog & TimePickerDialog are not retained on orientation change, you'd do a lot of work to retain them, this library simplify that.
* It uses DatePickerDialog & TimePickerDialog internally.
* Its simple to use.
* Its Customizable (Support Custom Themes). 
* Minimum API is 16, but it'll probably work in API 9 and above, just make sure you test it out (we use `Support Fragment`).  


# Dependency

Android Support Fragment Library ``v24.2.1``

**Pull requests are welcomed.**

# Copyright Notice

Copyright (C) 2016 Kosh.
Licensed under the [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
license (see the LICENSE file).
