# PTQ_daymatch
A project to test model performance when weather and streamflow cover the same 24 hour period vs when the 24 hours don't overlap

Traditionally at NVE, 24h hydrological models are driven by input data based on the synoptic meteorological observarion data, collected at 06 UTC. Thus, meteorological data cover the 24 hour period 06-06 UTC, i.e. 07-07 Norwegian normal time. Daily stremflow, however, is in the hydra2 database defined to cover the ordinary 24h day from 00-00. This means that on a spesific date, the associated precipitation fell from the day before at 07 o'clock up to the current day 07 o'clock, and the temperature is the estimated average over the same period, whereas the matching stream flow is the average over the current day. The weather data and the stream flow data thus have an overlap of only 7 hours. Since most of the precipitation and temperature represent the day before, particularily for small catchments, the simulated streaam flow is often delayed by sone day.

Now, dayly data are no longer necessarily restricter to these rigid time frames. The meteorological synoptic 24h data now exist in a 3 hourly version, disaggregated according to the pattern given by model hindcasts. These diaggregated time series cover the years 1958-2012 + 2015- (?). Thus, the meteorological 24h day can be redifined by reaggregating the 3h data to cover the 00-00 day. Alternatively, it is possible to redefine the stream flow day by aggregating fine scale data according to an arbitrary day definition. Fine scale stream flow data don't cover a very long time period. It was found that 127 out of the 145 flood forcasting stations have fine scale data from 1994, and 1994-2014 was chosen as the test period used here. Disaggregated met data are missing from 2012-2014. Traditional data are filled in for these two years in the corresponding data set. A test is set up to see whether the model performance (as shown by the HBV-model ) differs according to weather and stream flow 24h day definitions:

<b>Part 1:</b> The HBV-model, calibrated on traditional data, is run on the different data sets

<b>Part 2:</b> The HBV-model is calibrated and run on the different data sets

4 differen data sets are included in the test:

<b>1)</b> PT: 07-07, Q: 00-00 (traditional)

<b>2)</b> PT: 07-07 (the next day), Q: 00-00 (traditional with the weather 1 day delayed)

<b>3)</b> PTQ: 00-00 (using disaggregated weather data)

<b>4)</b> PTQ; 07-07 (using fine scale stream flow data)

