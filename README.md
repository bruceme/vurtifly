# VurtiFly
Personal vertical transport

# About

This is a project to create an all-electric UL/VTOL (ultralight vertical takeoff and landing) vehicle.

# Goals

* FAA Part-103 legal ultralight  
* Vertical take-off and landing
* Efficient horizontal flight capability 
* Carry one 180-lb adult pilot
* Fly for at least 30 minutes
* At least 20 miles range

# Inspiration

NASA Puffin Project

Horizon Hobby's X-Vert

# Airframe

I'm more impressed with the practical capabilities of the X-Vert.  For my "Mk-I" proof of concept, I'd like to simply scale it up to human-size.  That about 800-900% scale.  By applying appropriate multiples (4x for area 9x for volume/weight) That "back of the envelope" wild-alt guess yeilds...

## Specification _Approximation_

|           | X-Vert  | Vurtifly  |
|-----------|---------|-----------|
| Weight    | 200g    | 225.8 lbs |
| Span      | 504mm   | 13.3 ft   |
| Length    | 264mm   | 7.0 ft    |
| Wing Area | 7.8dm^2 | 54.4 sqft |

## Stress

The flight controller will limit G-loading to 2Gs internally, the aiframe will be designed and stress tested to a relatively low 3Gs. This is a very low stress level and easy to achieve in a light-weight airframe.

## Manufacture

The simple "wide-delta" shape has two simplifying benefits;
* Deltas have stable aerodynamic characteristics at extreme angles of attack.  This means it's much easier to control through horizontal to/from vertical transitions.
* It is a structurally simple shape easy to make very stiff with simple stress calculations

The airframe will be made by hot-wire-cutting EPS (Expanded Poly-Styrene) foam very similar to the popular Rutan aircraft.  A box-spar will be shaped to go under the pilot and contour to the wing as it taper into the engine mount structure mid-wing.  Common E-Glass fiberglass with aircraft-grade epoxy reason system will be used.  The entire surface of the airframe will have one or several layers of fiberglass to protect from handling damage and sustain any aerodynamic loads.

A set of aerodynamic winglets add both aerodynamic efficiency and mechanically support the aircraft on the ground with strategic rubber re-enforced hard-points in the trailing edge of the winglets.

# Motors / ESC

Two 100v-45kw Brushless DC motors.  I'm targetting the smalled 30-55 KV for low RPM and high torque.
The ESCs will be at least 500A and 120V capable.  

For both systems, I would like to avoid water cooling for simplicity of operation.

_Safety Note:_  Eventually I'd like to incorporate a custom doable-wound motor with dual controllers per powerplant.  The most common failure mode involves the motor controller.

# Propellor

Counter-rotating thin-blade composite propellors with a wide 60-70" diameter and small pitch of 30-50" will be most efficient for vertical lifting force and aid in limitting top-speed for part 103 in more efficient horizontal cruise.

# Batteries

Batteries are everything!  I have a complex spreadsheet that given motor parameters helps select appropriate battery/cell and configuration.  Note: this is for _ONE_ powerplant, x2 for complete system.

| Name                                | Nominal V | Current Cap | Capacity | Volume | mass | cost    | Max Disch | Cont Disch | S | P  | Cell Count | Volume | Nominal | Kwh | mass | cost      | Max Disch | Cont Disch | Specifc Energy |
|-------------------------------------|-----------|-------------|----------|--------|------|---------|-----------|------------|---|----|------------|--------|---------|-----|------|-----------|-----------|------------|----------------|
|                                     | V         | Ah          | Wh       | L      | g    | $       | A         | A          |   |    |            | Gal    | V       |     | kg   |           |           |            | Wh / Kg        |
| Chineese Alibaba "Special"          | 22.2      | 24          | 532.8    | 1.44   | 2972 | $180.00 | 1440      | 720        | 4 | 4  | 16         | 6.1    | 88.8    | 8.5 | 47.6 | $2,880.00 | 5760      | 2880       | 179.3          |
| Multistar High Capacity 20000mAh 6S | 22.2      | 20          | 444      | 1.08   | 2519 | $151.76 | 300       | 200        | 4 | 5  | 20         | 5.7    | 88.8    | 8.9 | 50.4 | $3,035.20 | 1500      | 1000       | 176.3          |
| Multistar High Capacity 12000mAh 6S | 22.2      | 12          | 266.4    |        | 1602 | $110.35 | 180       | 120        | 4 | 8  | 32         | 0.0    | 88.8    | 8.5 | 51.3 | $3,531.20 | 1440      | 960        | 166.3          |
| ZIPPY Compact 6200mAh 6s            | 22.2      | 6.3         | 139.86   |        | 889  | $59.99  | 315       | 252        | 4 | 14 | 56         | 0.0    | 88.8    | 7.8 | 49.8 | $3,359.44 | 4410      | 3528       | 157.3          |

_Configuration_

At this time, I see two physically seperate battery systems mid-wing behind and near each motor.  But they will be cross-linked in parallel throught the fuselage effectively make one large battery either motor system can feed from at will.

# Control

This is a unique control system as it is both a motor-lift "quad-like" hover vehicle and an aircraft.  In horizontal flight it is similar to a twin-engine delta fixed wing aircraft.  In horizontal mode, the motors power output is dynamically controlled to directly control yaw by the flight computer.  The flaps on the tralin  

There are four fundamental controls

The two motors control overall thrust and yaw
The two flap controls on the wing trailing edge are mixed in an "elevon" combined elevator & aeleron function.  This is a common control configuration for delta aircraft.  

## The "Stick" (Input device)

As a fly-by-wire, the input device is actually telling the flight-computer the pilot's "intent", not the exact input to any given control.  As such, it is entirely electronic.  The cockpit environment is also novel.  The pilot will be either standing upright on his/her feet or lying prone.  The flight-input and monitoring systems must work equally well in either orientation.

My initial concept is to mix the helicopter system with the common quadcopter.  The pilot's right hand will be on a 3D flight stick mounted with teh bottom on the wing-plane.  The left hand will have a "collective-like" spring-centered "stick" to control up/down in vertical mode.

## Strong Modality and mode-switch

Transitional modes (something between horizontal and vertical) have no advantage.  Using the X-Vert as a good example; it has binary horizontal or vertical mode toggle switch.  You are either in vertical or horizontal modes.  This switch will be gaurded.  Inadventent vertical to horizontal mode switch can be catestrophic as the flight controller assumes the pilot operator has cleared the space in-front of the vehicle for at least 500'.

## Horizontal Mode

Horizontal mode is "classic-delta" with the addition of differential engine thrust directly controlling yaw.  This will be managed via the flight computer and not at the pilots direct control.

## Vertical Mode

In vertical mode, engine thrust controls altitude.  Differential engine thrust controls yaw.  The Elevons will continue to control pitch and roll, but pitch-angle controls lateral position relative to the wing-normal vector.  This will all be controlled by the pilot using forward and back motion on the control stick.  Yaw (laterlaly) will be done via the "rudder" (twist on the 3-axis control) function.  Roll function and input remain classic.  This may seem unintuitive to a classic rotory wing control.  But remember the conrol stick is actually vertical in teh vertical configuration.  These motions are intuiative in this orientation.

# Balistic Parachute

A common Ultraligth Balistic Parachute system will be fitted to the top of the wing behind and near the pilot with embedded rip-out kevlar straps around and cradling the cockpit area similar to Cirrus.  This is a critical safety feature in case of catestrophic failure of the airframe, power or control systems.

# Final Notes

I created this help me keep my thoughts in one place and I find posting my research helps me pick up when I innevitably get distracted by another project.  This project does have significant importants and is a high priority in the long list of projects I have.  That said, I will likely lose track of it over time.  If you have any questions or want to know more, I invite you to reach out to me through comments on this repo.
