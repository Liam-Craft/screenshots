---
doctype: note
version: 0.1
tags: [timeline, Ar/Ceramics, test]

cssClass:
source:
---



timeline ⏬
```ob-timeline
tags=Ar/Ceramics;test
type=flat
```
timeline ⏫

<div class="ob-timelines"
	data-title="-200-130 : Gréco-Italiques"
	data-description=""
	data-classes=""
	data-color="blue"
	data-type="range"
	data-start-date="-200-01-00-00"
	data-end-date="-130-01-00-00"
	data-era=""
	data-path="Amphores Italiques#Gréco-italique"
	data-tags="">
</div>

<div class="ob-timelines"
	data-title="-130-70 : Dressel 1A"
	data-description=""
	data-classes=""
	data-color="green"
	data-type="range"
	data-start-date="-130-01-00-00"
	data-end-date="-70-01-00-00"
	data-era=""
	data-path="Amphores Italiques#Dressel 1A"
	data-tags="">
</div>

<div class="ob-timelines"
	data-title="-70-30 : Dressel 1B"
	data-description=""
	data-classes=""
	data-color="orange"
	data-type="range"
	data-start-date="-70-01-00-00"
	data-end-date="-30-01-00-00"
	data-era=""
	data-path="Amphores Italiques#Dressel 1B"
	data-tags="">
</div>

<div class="ob-timelines"
	data-title="-150-85 : Dressel 1C"
	data-description=""
	data-classes=""
	data-color="yellow"
	data-type="range"
	data-start-date="-150-01-00-00"
	data-end-date="-85-01-00-00"
	data-era=""
	data-path="Amphores Italiques#Dressel 1C"
	data-tags="">
</div>

<div class="ob-timelines"
	data-title="-50-25 : Imitations de Tarraconaise"
	data-description=""
	data-classes=""
	data-color="red"
	data-type="range"
	data-start-date="-50-00-00-00"
	data-end-date="-25-00-00-00"
	data-era=""
	data-path="Amphores Italiques#Dressel 1C"
	data-tags="">
</div>

<div class="ob-timelines"
	data-title="point"
	data-description=""
	data-classes=""
	data-color=""
	data-type="point"
	data-start-date="-50-01-00-00"
	data-end-date=""
	data-era=""
	data-path=""
	data-tags="">
	New Event
</div>

**⚠️ this one is not working**
<div class="ob-timelines"
	data-title="50+200 : Dressel 2-4"
	data-description=""
	data-classes=""
	data-color="orange"
	data-type="range"
	data-start-date="50-01-00-00"
	data-end-date="200-01-00-00"
	data-era=""
	data-path="Amphores Italiques#Dressel 2-4"
	data-tags="">
</div>

- if start date is *negative*, the timeline doesn't render
	- throws *plugin:timelines-revamped:25145 Couldn't create a luxon date string!*
	- and *Uncaught (in promise) Error: Property "end" missing in item 5*
- if start date is *positive*, the timeline render but not this range.


# Also...
looking through debug messages, one of the *buildHorizontalTimeline | there is an endDate for event* object is:
```
normalizedAndCleanedDateObject: {
    "cleanedDateString": "-50-0-0-0",
    "year": -50,
    "month": -1,
    "day": 0,
    "hour": 0,
    "normalizedDate": "-00050-00000-00000-00000"
}
```
is it normal for *month* to normalize to -1 instead of 0 given the original date ? (I'm not familiar at all with date-string magic....)