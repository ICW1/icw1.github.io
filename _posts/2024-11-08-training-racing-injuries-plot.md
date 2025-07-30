---
layout: post
published: True
title: Visualisations of my Training + Racing + Injuries
---

#### Intro
If you're reading this, you probably know I'm a keen runner. I've been running since junior school and have been fortunate enough to train and compete all over the world with some incredible athletes. The following graph visualises the last 10 years of my athletic career. I created it with <!--more-->the following data:
* Weekly running mileage. Retrieved from from Garmin Connect via the [python API](https://pypi.org/project/garminconnect/0.1.53/), processed and aggregated with Pandas to give weekly totals.
* Race data. Scraped from [Power of 10](https://www.thepowerof10.info/), a database of all athletes and races maintained by UK athletics, using [*power of 10 API from Will Mycroft*](https://github.com/willmycroft/po10-api) (thanks Will!)
* Injury data. Manually entered via my own training diary and medical history.

I created the following plot to better understand my training load. I've competed well but I've had a lot of injuries. I've had a higher frequency of injuries more recently. This includes two very large injuries with almost a year of rehabbing and running in pain for each. I created the plot to better understand how volume and racing relates to injury risk.

#### Visualisation:
![an image alt text]({{ site.baseurl }}/images/my_running.png "Overall traiing + racing + injuries")

#### Explanation:
The top annotations indicate the locale I was based:
- Brighton - my home town. I started to train seriously in 2013/14. 
- Birmingham 2014-2017 - Started my undergraduate degree at the Univserity of Birmingham. It had a great athletics group!
- University of New Mexcio 2017-2019 - Master's degree. Scholarship to compete in the NCAA. A great experience and environment with lots of serious training!
- London - where I've lived since 2019. I also worked a full time job since then. 
- London GW - when I was training with World Champion Jake Wightman under coach (and Jake's father) Geoff Wightman

#### Findings:
1. I tend to get an injury when I change to a new environment. i.e. starting at Birmingham, New Mexico or changing group. When coming back from America I was aware of this, and purposefully dialled back the running as I started work.
2. Injuries tend to follow periods of extreme mileage, high intensity and frequent track racing.
3. My most consistent periods of trianing came when not exceeding 70 miles per week.

#### Recommendations:
1. Limit mileage to ~70 miles / week. This is good because it means I can take 1 rest day / week. 
2. Prioritise consistency. Allow for balance between work and training.
3. Don't do too many races in quick succession.

Lastly, injuries happen. Sometimes they are totally out of our control. But there are definitely steps we can take to mitigate this. Hopefully some of the suggestions above will work!


#### notes
Will share the various code soon.


