Quake
=====

Quake is a library exposing the U.S. Geological Survey's real-time earthquake data. As described on [USGS' Earthquake Hazards Program](http://earthquake.usgs.gov/earthquakes/), "earthquake information is extracted from a merged catalog of earthquakes located by the USGS and contributing networks. Earthquakes will be broadcast within a few minutes for California events, and within 30-minutes for worldwide events".

Installation
------------

via Gem:

    [sudo|rvm] gem install quake

via Bundler:

    gem "quake"

Basic Usage
-----------

Fetch all the earthquakes from the past week:

    events = Quake::Event.last_week

Fetch all the earthquakes from the past day:

    events = Quake::Event.last_day

Fetch all the earthquakes from the past hour:

    events = Quake::Event.last_hour

Fetch all the earthquakes from the past [week|day|hour] with minimum and/or maximum magnitudes:

    events = Quake::Event.last_week :min_magnitude => 3
    events = Quake::Event.last_week :max_magnitude => 4
    events = Quake::Event.last_week :min_magnitude => 3, :max_magnitude => 4

Fetch all the earthquakes from the past [week|day|hour] with a minimum and/or maximum magnitude at or near a location (in km):

    events = Quake::Event.last_week :min_magnitude => 2, :epicenter => "37.156, -117.3723"
    events = Quake::Event.last_week :min_magnitude => 2, :epicenter => "37.156, -117.3723", :distance => 100

Questions or Problems?
----------------------

If you have any issues, please [add them to GitHub](https://github.com/chrisbaglieri/quake/issues) or fork the project and send a pull request (with tests of course). The tests are very straight forward, nothing more than minitest; yay for simplicity!