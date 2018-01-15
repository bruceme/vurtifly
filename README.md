# VurtiFly
Personal vertical transport

![alt text](http://4.bp.blogspot.com/_kHK4gpOKyDU/SPdYxux833I/AAAAAAAAAnk/c6vQvXEPJ9I/s1600/birdman.jpg "VurtiFly man flying")


# About

This is a project to create an all-electric UL/VTOL (ultralight vertical takeoff and landing) vehicle.

# Goals

* FAA Part-103 legal ultralight  
   * Single-pilot / recreation
   * Empty Weight < 254 lbs
   * "Fuel" Quantity <= 5-US Gal; (18L of battery volume ~ 9kwh)
   * Calibrated Airspeed <= 55 knots
* Vertical take-off and landing
* Efficient horizontal flight capability 
* Carry one 180-lb adult pilot
* Fly for at least 30 minutes
* At least 20 miles range
* Low-noise, neighbor friendly

# Inspiration

[NASA Puffin Project](https://www.nasa.gov/topics/technology/features/puffin.html)

[![NASA Puffin Video](https://theawesomer.com/photos/2010/01/012010_puffin_t.jpg)](https://www.youtube.com/embed/QSdwNl-9mPU "NASA Puffin Video")

[Horizon Hobby's X-Vert](https://www.horizonhobby.com/x-vert-vtol-bnf-basic-efl1850)

[![X-Vert Video](https://hobbyohio.com/wp-content/uploads/2017/06/E-flite-X-VERT-VTOL-RTF-EFL1800-16.jpg)](https://www.youtube.com/embed/wFXibbgNix8 "X-Vert Video")

Pancakes Anyone?
![Flying Pancake](https://upload.wikimedia.org/wikipedia/commons/2/20/Vought_V-173.jpg "Flying Pancake")

# Airframe

I'm more impressed with the practical capabilities of the X-Vert.  For my "Mk-I" proof of concept is X-Vert, scaled up to human-size.  That's about 680% scale.  By applying appropriate multiples and calculating "back of the envelope" wild aeronautic guess yeilds...

## Specification _Approximation_

|              | X-Vert  | Vurtifly       |
|--------------|---------|----------------|
| Weight       | 200g    | 225.8 lbs      |
| Span         | 504mm   | 11.2 ft        |
| Length       | 264mm   | 5.9 ft         |
| Wing Area    | 7.8dm^2 | 42.2 sqft      |
| Wing A/R     |         | 3.7:1          |
| Wing Loading |         | 10.02 lbs/sqft |
| Cabin width  |         | 2.4 ft         |

![Dimensions](image/vurtiflydimensions.png)

## Stress

The flight controller will limit G-loading to 2Gs internally, the aiframe will be designed and stress tested to a relatively low 3Gs. This is a very low stress level and easy to achieve in a light-weight airframe.

## Manufacture

The simple "wide-delta" shape has two simplifying benefits;
* Deltas have stable aerodynamic characteristics at extreme angles of attack.  This makes it more stable and predictable through horizontal/vertical flight transition.
* It is a structurally simple shape, easy to make very strong with well-known aircraft structures.

The airframe will be made by hot-wire-cutting XPS (Extruded Polystyrene or Styrofoam Fabrication Billets) foam very similar to the popular Rutan aircraft.  A box-spar will be shaped to go under the pilot and contour to the wing as it taper into the engine mount structure mid-wing.  Common E-Glass fiberglass with aircraft-grade epoxy reason system will be used.  The entire surface of the airframe will have one or several layers of fiberglass to protect from handling damage and sustain any aerodynamic loads.

The HS522 is a widely used low-moment airfoil seems appropriate, it's good general purpose high flying wing.
![hs522](https://www.aerodesign.de/profile/hs522.gif)

A set of winglets add both aerodynamic efficiency and landing skids.  The winglett trailing edge will have rubber pads and rollerblade wheels to allow the Vurtifly land solidly and facilitate ground handling. 

# Motors / ESC

Two 100v-45kw Brushless DC motors. Approx. 30-55 KV for low RPM and high torque.
The ESCs will be at least 500A and 120V capable.  

For both systems, avoid complex water cooling, but limits continous high power 

# Propellor

Counter-rotating thin-blade composite propellors with a wide 60-70" diameter and small pitch of 30-50" will be most efficient for vertical lifting force and aid in limitting top-speed for part 103 in more efficient horizontal cruise.

If the aircraft makes too much noise, it will never have wide-spread use outside accepted noise-poluted locations.  The following atributes directly improve propellor noise generation;
* Longer blades
* Fewer blades
* Fatter blades
* Slower RPMs (tip speed)
* Low-noise profiles

!["Low noise props"](https://proxy.duckduckgo.com/iu/?u=http://www.nwuav.com/images/uav-propellers/TigersharkProp-rotated.jpg "low noise props")

A counter ballanced and cantaleaved single bladed props can be longer, fatter and slower for noise abatement and efficient propulsion on smaller power applications. This was proven on the Alisport Silent-In.
![single blade prop"](https://upload.wikimedia.org/wikipedia/commons/f/f1/Single-blade_propeller_drawing.gif "single blade prop")

I don't believe any hovering aircraft can be "quiet" but it can be orders of magnitude quieter than legacy rotorcraft and other vertical flight systems.  Potentially this could drop bellow a threshold of reasonable announce for common uses.

!["Posibilities"](/image/VTOLFuture.jpg)

If this problem can't be solved, VTOL will remain limitted to operating from the limitted/established airports and heliports.

# Batteries

Batteries are everything!  Given motor parameters, this complex spreadsheet helps select appropriate battery/cell and configuration.  Note: this is for _ONE_ powerplant, x2 for complete system.

| Name                                | Nominal V | Current Cap | Capacity | Volume | mass | cost    | Max Disch | Cont Disch | S | P  | Cell Count | Volume | Nominal | Kwh | mass | cost      | Max Disch | Cont Disch | Specifc Energy |
|-------------------------------------|-----------|-------------|----------|--------|------|---------|-----------|------------|---|----|------------|--------|---------|-----|------|-----------|-----------|------------|----------------|
|                                     | V         | Ah          | Wh       | L      | g    | $       | A         | A          |   |    |            | Gal    | V       |     | kg   |           |           |            | Wh / Kg        |
| Chineese Alibaba "Special"          | 22.2      | 24          | 532.8    | 1.44   | 2972 | $180.00 | 1440      | 720        | 4 | 4  | 16         | 6.1    | 88.8    | 8.5 | 47.6 | $2,880.00 | 5760      | 2880       | 179.3          |
| Multistar High Capacity 20000mAh 6S | 22.2      | 20          | 444      | 1.08   | 2519 | $151.76 | 300       | 200        | 4 | 5  | 20         | 5.7    | 88.8    | 8.9 | 50.4 | $3,035.20 | 1500      | 1000       | 176.3          |
| Multistar High Capacity 12000mAh 6S | 22.2      | 12          | 266.4    |        | 1602 | $110.35 | 180       | 120        | 4 | 8  | 32         | 0.0    | 88.8    | 8.5 | 51.3 | $3,531.20 | 1440      | 960        | 166.3          |
| ZIPPY Compact 6200mAh 6s            | 22.2      | 6.3         | 139.86   |        | 889  | $59.99  | 315       | 252        | 4 | 14 | 56         | 0.0    | 88.8    | 7.8 | 49.8 | $3,359.44 | 4410      | 3528       | 157.3          |

_Configuration_

Two physically seperate battery systems mid-wing behind and near each motor.  But they will be cross-linked in parallel throught the fuselage effectively make one large battery either motor system can feed from at will.

_Future_

Lithium Sulfer chemistry is very promising. It will likely double and potentially triple the specific energy density (grams per kwh).  That goes right to the range for a given weight of battery capacity.  With this technology minimally altered future version of the Vurtifly could fly for 2 hours with reserve and go 300 miles at very high altitudes and economy. 

# Control

This is a unique control system as it is both a motor-lift "quad-like" hover vehicle and an aircraft.  In horizontal flight it is similar to a twin-engine delta fixed wing aircraft.  In horizontal mode, the motors power output is dynamically controlled to directly control yaw by the flight computer.  The flaps on the tralin  

## Four Controls

The two motors control overall thrust and yaw
The two flap controls on the wing trailing edge are mixed in an "elevon" combined elevator & aeleron function.  This is a common control configuration for delta aircraft.  

## Flight Controller

There are several good open source project to work from, but for now, I've narrowed it down to [betaflight](https://github.com/betaflight/betaflight)

This is a fork of CleanFlight and is considered the latest and most feature rich.  One of the out-of-the-box supported flight modes is called "bicopter".  It's two motors + 2 servos.  Flashed a basic 10-DoF Flip32+ controller immediately got all 10-DoFs (3-acc, 3-gyro, 3-mag, 1-altitude) to work and calibrate.  Additionally a GPS can be added for stabalized position hold and navigation as well as a sonar for very accurate AGL hover-hold and potentially auto-landing.

## You're Crazy!

That could very well be, but... why not, it's worth a shot and here's why.

The PID Control Loop running in these cheap R/C controllers is actually state-of-the-art.  It has all the same sensors much more expensive controllers had 10 years ago, it's just smaller.  And finally, controlling something small is actually _MUCH_ harder than controlling something big.  Big things have mass. from F=M*A; re-orgnized A=F/M.  So accelleration is an inverse function of mass for a given amount of force.  If small thigns react faster, you have to correct those forces _MUCH_ faster.  So more mass, slower, easier, simpler; but all the same controls and there's no reason to believe this won't work, once I've adjusted the gains with initial flight testing.

## The "Stick" (Input device)

Fly-by-wire implies the pilot is not directly commanding any specific control.  A human pilot is incapable of manually controlling this complex set of inputs safely and with the speed it requires.  Instead a fast processor with attitude sensors is commanding the motors and flight surfaces.  The pilots role is to command the computer with his intent to direct the craft for safe operation.  These inputs will be intuitive using legacy flight paradigms like helicopters and aircraft.  But commanding will be simple "first order" inputs (go forward,left,right,up); not the exceedingly complex second and third order crossing-inputs common to rotorcraft and aircraft (pitch forward, yaw left, collective up/down).  This means learning to fly it will be trivial compared to rotorcraft and even aircraft.

As such, this system is entirely electronic.  The cockpit environment will be novel.  The pilot will be either standing upright on his/her feet or lying prone.  The flight-input and monitoring systems must work equally well in either orientation.

![Prone pilot](http://robotpig.net/_images/posts/puffin_1.jpg "Prone Pilot")

My initial concept is to mix the helicopter system with the common quadcopter.  The pilot's right hand will be on a 3D flight stick mounted with the bottom on the wing-plane.  The left hand will have a "collective-like" spring-centered "stick" to control up/down in vertical mode.

## Strong Modality and mode-switch

Transitional modes (something between horizontal and vertical) have no advantages.  Using the X-Vert as a good example; it has binary horizontal or vertical mode toggle switch.  You are either in vertical or horizontal modes.  This switch will be gaurded.  Inadventent hover to forward-flight mode switch can be catestrophic as the flight controller assumes the pilot operator has cleared the space in-front of the vehicle for five hundred feet or more.

Some videos of the X-Vert show it dropping while transitioning from hover to forward-flight modes.  This is concerning.  It doesn't appear to be the flight controller.  The pilot's input is too rapidly changing purpose.  In hover mode, the forward stick is "cyclic" or "traverse foreward".  In flight-mode that same input means "dive".  So the craft is instantly switching from hover to flight and an incipient "dive" is inadvertently commanded while the pilot's head catches up to the modality switch.  Gradually fading the controls from hover to forward-flight will give the pilot the ability to stay ahead of it.  Ideally normal operations hover to forward transitions would actually be made in an intentional climb for ground obstacle avoidance.

For all the reasons stated above, artificially inserting a mandatory modest climb in the hover to forward transition may be a wise safety precation.

## Horizontal Mode

Horizontal mode is "classic-delta" with the addition of differential engine thrust directly controlling yaw.  This will be managed via the flight computer and not at the pilots direct control.

## Vertical Mode

In vertical mode, engine thrust controls altitude.  Differential engine thrust controls yaw.  The Elevons will continue to control pitch and roll, but pitch-angle controls lateral position relative to the wing-normal vector.  This will all be controlled by the pilot using forward and back motion on the control stick.  Yaw (laterlaly) will be done via the "rudder" (twist on the 3-axis control) function.  Roll function and input remain classic.  This may seem unintuitive to a classic rotory wing control.  But remember the conrol stick is actually vertical in teh vertical configuration.  These motions are intuiative in this orientation.

## Holds and Navigation

The flight controller had several stock modes that can be used to precisely position and navigate the VurtiFly. 

* GPS Position - Hover hold at any altitude with accuracy within 10 meters.  Appropriate takeoff, hover and approach
* GPS Heading & Altitude - Will hold a GPS heading and pressure altitude.  Enabled enroute navigation to a GPS destination from Navigation devices [Avare](https://apps4av.com/avare-overview)
* Sonar Hold - Will hold better than a centimeter accurate sonar altitude at any height less than 1.5 meters.  Very useful for precise landings.  Will be used with hover to stabalize the last 1.5 meters for imperceptibly soft landings.

# Safety Items

## Future redundancy

Brusheless electric motors are a foundational element of this design.   When correctly engineered, sized and tested for a given application they are oustandingly reliable. Unfortunately most failure modes are not gradual with obvious indications of imminent issues; failures are typically instantanious and complete.  For that reason redundency must be designed into the system accounting for common failures.

Common failure modes;
- Wiring continuity
- Motor controller
- Battery fire
- Motor overheating
- Servo
- Flight controller
- Bird/Prop Strike

For all these reasons some level of redundancy should be considered.

### Powerplant Redundancy

The common BLDC / ESC have a rarely utilized design facet that enables obvious redundancy.  A "double wound" motor has two sets of coils to the same stator arms.  each winding set can have it's own independant (synchronized) motor controller.  You can operate that motor at full power on both and a slightly reduced power on either one.  Both controllers must be operating to initiate safe flight, but failure of either controller in flight will trip the master alarm and immediate landing is recomended.   But a safe precautionary landign can be accomplished on either controller with a limitted hover.  Continous high power hovering operation on one coil will result in overheating and eventual secondary system failure.

The battery -> controller -> motor -> prop is the powerplant.  Both powerplants must be capable of producing minimal landing trust to conduct safe flight operations.  This is a more robust powerplant design that can accomidate motor controller and coil failure and some wiring failure modes.

![Powerplant Design](https://docs.google.com/drawings/d/e/2PACX-1vRxgDvA9QpZh6BhW-pnYit-M7pkruSlULpIn0dItlDGl9pG5X4ds_HKExQzT472MQDzSj_qCs87GuR1/pub?w=622&amp;h=697 "Powerplant Design")

### Servo redundancy

Internally servos are comprised of a set of reduction gears connected to a brushless motors with a small controller and using a position sensor.  A novel dual redundent servo can be fabricated that shared mechanical hardware and redundant motor, sensors and controllers as these are the common failure modes in servos.  This is similar to the motor powerplant redundancy described above but for servo controller system. 

![Servo cross section](https://i0.wp.com/www.icrobotics.co.uk/wiki/images/1/19/Servo_Stripped.jpg "Servo Cross Section")

## Balistic Parachute

When all the redundencies fail and options eliminate quickly, a zero-altitude parachute is wise.

A common Ultraligth Balistic Parachute system will be fitted to the top of the wing behind and near the pilot with embedded rip-out kevlar straps around and cradling the cockpit area similar to Cirrus.  This is a critical safety feature in case of catestrophic failure of the airframe, power or control systems.

In case of battery fires, a second "dual-handle" will eject the batteries.

# Final Notes from the Author

I created this page to help me gather my thoughts in one place and find a home for all my research.  So when I innevitably get distracted by another project, I can pickup from this spot quickly.  This project does have significant importants and is a high priority in the long list of projects I have.  That said, I will likely lose track of it over time.  If you have any questions or want to know more, I invite you to reach out to me through comments on this repo.
