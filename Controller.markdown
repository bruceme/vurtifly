# What are the current projects

- CleanFlight
- BetaFlight
- iNavFlight
- OpenAeroVTOL

## *Flight
The *Flight are all related projects that started from "BaseFlight".  It is kept up to date and updates are frequent.  It also runs on the latest boards.  CleanFlight is the least aggressive and mostly targetted at Drone. iNavFlight is targetted for GPS navigated vertical and flight vehicles.  BetaFligth is where new/cutting edge features go and all three projects moosh around pull requests.

All these controllers are missing VTOL capability.  Some folks have cobbled them together, but they are lacking any concept of a mode or mode switching.  The vehicle is what you set it up to be.

## OpenAeroVTOL

This was an extension of the OpenAero project, it only runs on one board the "KK2.1.5" and it does not appear to have any active followers at this time.  It's whole purpose for being is that it support modes and control/PID mixes through transition.  It seems a bit "left behind" and I can't seem to find much on what is needed.

# What should a VTOL controller do?

- Open Source
- Good readily available boards
- Big community
- A good copter control
- Multiple control and PID mixes
- Different modes of flight
- Control in and through different modes

# Updating *Flight project?

*Flight has many of the hardest attributes I'm looking, but it's lacking some technical pieces.  It needs to support modes and different control and pid mixes in different modes.  I also don't feel it's navigation modes will function well appropriate for what I need.  Ideally I want to be able to also specify two aircraft in one controller, one vertical aircraft with it's controls and another horizontal flight aircraft with seperate controls and PIDs.  Then have the controller attempt to mix the two as it transitions into forward flight.
