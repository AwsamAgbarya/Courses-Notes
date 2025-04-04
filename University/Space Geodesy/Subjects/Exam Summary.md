# Coordinate Reference systems
### Coordinate systems:
>[!note] Definition
>**Coordinate systems** are the mathematical basis in the metric space that define the conventions and the order of the coordinate locations.
>
>**Coordinate systems** are built form an *orthonormal basis unit vectors* called basis or triad. The basis axes are *linearly independent* and share the origin point
- Cartesian coordinates describe position while spherical/elliptical coordinates are mainly orientational.
- The metric tensor describes us how far two points are in each unit of distance in the system on the manifold (allows us to define distances on a manifold in different systems).
### Reference systems:
##### Terminology:
- **Solar System Barycenter:** the center of mass of every object in the solar system combined.
- **Principal Plane:** The plain (Declination = 0) of an orientational coordinate system.
- **Declination:** Angle from vector to the equatorial plain.
- **Inclination:** Angle from vector to pole.
- **Azimuth:** for an observer the azimuth is the horizontal angle from the north.
- **Zenith:** for an observer the zenith is the direct vector upwards (Plumb line: The local gravity direction).
- **Celestial plane:** is the plane that uses the celestial equator projected across the universe, and the celestial equator is earth's equator.
- **Ecliptic plane:** the plane that models the orbit of earth around the sun.
- **ECEF:** rotates with earths rotation 
- **ECI:** doesnt rotate with earth, so coordinates change over time.
- **Inertial system:** Non-accelerating system i.e velocity is constant and it does not rotate, newtonian lines apply thus a mass at rest will have F=0 (no ficticous forces).
- **Non-inertial systems:** Accelerating system i.e velocity is changing whether in speed or direction, in order to model mass at rest we add ficticious forces in space because gravity is seen as deformation of space time not a force.
##### International Celestial (ECEF):
- **Time:** Barycentric coordinate time.
- **Origin:** Barycenter of solar system.
- **Principal plane:** Celestial equator at equinox J2000.
- **Right ascension:** The point where the mean ecliptic intersects the true celestial equator at equinox J2000.
##### Geocentric Celestial (ECI):
- **Time:** Geocentric coordinate time.
- **Origin:** Geocenter of earth.
- **Principal plane:** Celestial equator at equinox J2000.
- **Right ascension:** The point where the mean ecliptic intersects the true celestial equator at equinox J2000.
- **Ellipsoidal Model:**
	- a mathematical shape that represents this flattened sphere which is used by these models designed to fit the Earth's crust as accurately as possible across the globe.
- **Geoid Model:**
	- model of Earths mean sea level and represents the shape of the Earth under the influence of gravity and rotation, including mass variations in earth.
	- The strength of the gravity potential is stored as spherical harmonic coefficients (SHC).
##### International Terrestrial (ECEF):
- **Time:** Geocentric coordinate time.
- **Origin:** Geocenter of earth.
- **Principal plane:** Earths equator.
##### Local topocentric horizon:
- **Time:** Terrestrial local time.
- **Origin:** Topocenter.
- **Principal plane:** local horizon.
- **Right ascension:**  North.
### Time:
###### Atomic time scale:
- **TAI:** A continuous time scale based on ~450 atomic clocks worldwide without leap seconds.
- **UTC:** TAIs civil counterpart, adjusted with leap seconds to stay within ±0.9s of UT1.
###### Earth time scales:
- **UT1:** Measures Earths rotation angle relative to distant stars (VLBI) based on the apparent path of Sun as seen from the Earth
- **GMST:** The hour angle of the mean vernal equinox at the Greenwich meridian without nutation which is derived from UT1.
- **GAST:** Includes corrections for nutation.
###### Relativistic time scales
- **TT:** The coordinate time defined on the geoid
- **TCG:** Time scale for Earth-centered (geocentric)
- **TCB:** Time scale for the solar systems barycenter.
######  Time reference systems:
- **JD and MJD:** time in days (and fractions of days as decimal) since the reference epoch 1st Jan 2000, MJD is the same but the first two digits are truncated.
- **Gregorian calendar:** calendar works with an average year length of 365.2425 days.
# Earth's Orientation
>[!note] Definition
>Modelling earths instantaneous orientation, due to many earth and celestial processes.
>Used to transform from an ECEF to ECI systems.
##### Polar Motion:
>[!Note] Definition
>natural movement of Earths rotational axis relative to its surface which causes the geographic locations of the North and South Poles to slowly drift over time.
- **Components:**
	- *Perioidic:*
		- Chandler wobble: driven by movement in Earths internal structure such as Mantle convection, tectonic shifts.
		- Annual Wobble: caused by more seasonal changes like air pressure distribution of water and ocean currents.
	- *Long term effects:*
		- Polar Wander:  mass redistribution on Earths surface including Intrinsic processes like mass pumping of ground water, icecaps melting, the dynamics of the liquid outer core, particularly the motion of molten iron, tectonic plate movement, Isostatic adjustments.
##### Precession and Nutation:
>[!Note] Definition
>**Precession** is the slow, conical movement of Earth's rotational axis around pole of ecliptic.
>**Nutation** is a periodic version of Precession.
- **Causes:**
	- caused by gravitational forces applying torque (change in angular momentum) onto a rotating object. This is mainly exerted by the closest and the densest objects namely the moon and sun.
	- *Tidal Friction:*
		- The moons gravity makes bulges in earths shape (Oceans especially).
		- Earth rotates faster than the moon's orbit.
		- This causes the moon to pull back on those bulges and apply torque on earth slowing it down.
		- The bulges also apply torque on the moon causes it to go further from earth to conserve angular momentum.
		- This causes period changes in the axis.
# Satellite Orbits:
##### Terminology:
- **Centripetal force:** Force acting inwards in an orbit.
- **Centrifugal force:** Ficticious force acting opposite of Centripetal force to keep the object at rest in a non-inertial frame.
- **Coriolis force:**  Ficticious force acting on objects changing orbit radius to properl them forward.
- **Euler force:** Ficticious force acting on objects that are changing angular velocity to push them inwards or outwards.
- **Angular velocity:** Rate of change of rotation angle.
- **Torque:** Rotational force causing angular acceleration.
- **Inertia:** Resistance to changes in speed.
- **Moment of Inertia:** Resistance to changes in angular velocity.
- **Momentum:** Quantity of motion in a straight line
- **Angular momentum:** Quantity of rotational motion.
- **Equinox:** The vernal (spring) equinox and autumnal (fall) equinox are the two points where the ecliptic intersects the celestial equator and the length of day and night is equal.
- **Soltuces:** The two points in Earths orbit where the Sun reaches its highest or lowest position in the sky at solar noon, relative to the celestial equator
###### Orbital Parameters:
- **Ellipsoidal:**
	- *semi major axis a:* Half the length of the longest diameter of the ellipse.
	- *semi minor axis b:* Half the length of the shortest diameter of the ellipse.
	- *eccentricity e:* Measures how "stretched" the ellipse is
	- *flattening f:* A measure of how "squashed" an ellipse is along its minor axis. 
- **Locational:**
	- *True anomaly v:* the angle between the object and the Periapsis
	- *Eccentric anomaly E:* the angle between the pericenter and the objects position, projected onto a circumscribed circle around the ellipse.
	- *Mean anomaly M:*  the centric angle from the periapsis to an auxiliary point at the circle of radius a after time ∆𝑡 elapsed.
	- *Mean moition n:* the corresponding constant angular velocity magnitude of mean anomaly.
- **Orientational:**
	- *Periapsis:* The closest point on the ellipse to the center (one of the focal points).
	- *Apoapsis:* The furthest point on the ellipse to the center (one of the focal points).
	- *Ascending node:* The point where an orbiting object crosses the reference plane, opposite of the descending node.
	- *Inclination:* Tilt relative to the reference plane which is usually the equatorial plane
	- *Right Ascension of the Ascending node:* The angle measured eastward from the vernal equinox to the ascending node in the reference plane.
	- *Argument of periapsis:* The angle from the ascending node to the Periapsis of the orbital plane measured in the orbital plane along the satellites direction of motion.
###### Keplers Laws:
- Planetary orbits are ellipses with the sun as one focal point.
- Planets sweep equal areas at equal times.
- Orbital period is proportional to semi major axis or orbit.
###### Orbital Energy:
- Objects in orbit exhibit potential and Kinetic energy.
- Due to energy conservation, it will always balance out in a stable orbit.
- In circular orbits the energy does not exchange.
- In ellipsoidal energy the kinetic energy gets bigger around the periapsis because the potential energy decreases and vice versa.
###### LEO (200-2000KM):
- Requiring around about 8 km/s to maintain orbit and have an orbital period of around 90m.
- Can be equatorial which are easy to launch or polar which cover earth better depending on their inclination.
- Remote sensing, ISS, Space Shuttle.
###### MEO (5000-20000KM):
- Requiring around about 4-6 km/s to maintain orbit and have an orbital period of around 3–12h. 
- Navigation GPS Galileo, gravity field mapping (LAGEOS)
- very stable orbits
###### GEO (35790KM):
- Requiring about 3.9 km/s to maintain orbit and  move at the same angular velocity as the Earth rotate.
- global communication and TV broadcasting.
###### Pertubation:
- **Non-Grav:**
	- Atmospheric Drag.
	- Solar Radiation Preasure.
- **Gravitational:**
	- Tidal Effects
	- Third body effects from other solar masses.
	- Earths non spherical gravity.
###### Numerical integration:
- **Euler:**
	- Non-accurate even with small h.
	- Only one step at a time calculation.
- **RK4:** 
	- fourth order method
	- order h^4 
- **Multi step:**
	- Use previous steps to construct a polynomial approximation which will predict the next point + help us with integration.
- **Encke method:**
	- integrate orbit pertubations w.r.t the reference orbit dealing with smaller numbers allows it to achieve higher accuracy with less integration steps.
# GNSS
>[!Note] Definition
>Navigation is any method of real-time trajectory and velocity planning a ship's or aircraft's position and course by geometry, astronomy, radio signals etc
- **Position Fixing:**  Determines location by measuring distances/angles to known reference points such as observation stations and satellites. These techniques include Time of flight and time of arrival and time difference of arrival.
- **Dead Reckoning:** Estimates position by integrating motion over time (measured by inertial sensors) it is prone to error accumulation over time. we need accurate time data and velocities over time to estimate trajectories.
- **Pseudo-range:** the range measurement from Transmitter to receiver which can include many errors and infleunces such as atmospheric delays, clock delay errors, Reflected pathways and Ephemeris position inaccuracies.
- **Autonomous vs Cooperative:** Autonomous is completely independent and does not rely on external stations, whilst cooperative continuously communicated with facilities to improve accuracy (Like auto cars).
###### GNSS Segments:
- **Space Segment:** Which is the entirety of operations space vehicles broadcasting signals and navigation data
- **User Segment:** All the navigation receivers (GPS, GLONASS) and the processing software.
- **Control Segment:** Earth tracking stations, Infrastructure and software for the monitoring and operation of the navigation systems.
	- *Master control station:*  the central hub for processing satellite data and managing the entire satellite constellation
- **Ground Segment:** The global network of ground stations that track satellites and relay data to the Control Segment.
	- *Ground control stations:* Ground antennas communicate directly with satellites.
	- *Monitoring stations:*  continuously tracking the satellites and equipped with precise dual frequency receivers high quality meteorological stations
###### Ranging Methods:
- Using radio frequencies from 10kHZ to 300GHZ.
- Time of Flight: The atomic clock records time of transmission on satellite and send the signal to earth which is then compared with time of arrival while accounting for clock errors, multipled by the speed of light to get the range.
- **Code ranging:** 
	- Uses PRN on both sides and measures the misalignment of the signal after arrival.
	- Complex and mm accuracy but sensitive to obstructions
	- Different receiver and sender clock errors are taken into account.
	- Clock correction and orbit parameters are sent by satellite.
	- $R = c(T_{r}- T_{s}) + c(u_{r}- u_{s}) + (\alpha_{r}- \alpha_{s})$
- **Carrier Phase:**
	- Electromagnetic waves are harmonics and have a phase, which is the angle of the signal in its cycle.
	- 2 x pi x f: is the angular velocity of that wave.
	- Meters accuracy and simple
	- This introduces an integer ambiguity term that is constant to account for how many cycles have passed.
	- Signal is also received with doppler effect according to the relative velocities.
	- $R = c(T_{r}- T_{s}) + c(u_{r}- u_{s}) + \lambda(N + \alpha_{r}- \alpha_{s})$
- **Biases:**
	- Ionospheric refraction
	- Tropospheric refraction
	- Clock errors
	- Hardware errors
	- Orbit errors
	- reflections and multi paths
	- radio interference
- **GPS:**
	- electromagnetic wave carrying navigation signals and messages continuously propagating from orbiting satellites towards earth.
	- $S = \sqrt{2A} \cdot C \cdot D \cdot \cos(2\pi f_{ca}t+\phi_{ca})$
	- *Coarse Aquisition:* a unique, repeating binary sequence assigned to each GPS satellite used for the initial acquisition and tracking of the L1 signal. 10m accuracy
	- *P Code:* high-precision, long, encrypted pseudo-random noise sequence on L1 and L2 frequency. 1m accuracy, encrypted with W code to have anti spoofing results in Y code
	- meters accuracy if not augmented.
	- L1, L2 L5 RF waves.
	- signal/noise ratios and doppler observables.
###### Data recording approaches:
- *Static:* Stationary for hours + post processing
	- *Post processing:* Analyzed and refined using data correction
- *Kinematic:* the receiver is moving or stop and going.
	- *Real time:* provides live positioning as its pre processed during collection.
- *Absolute:* a single GNSS receiver is determined directly with reference to the satellite positions (10-30m)
	- *Precise Point Positioning:* use precise satellite orbit and clock corrections available from external sources to improve positioning accuracy.
- *Relative:* the position of a receiver is determined relative to the base station (mm-cm)
	- *RTK (semi kinematic):* The base station broadcasts correction data to the rover in real time, allowing for accurate position estimates, uses both carrier and code. (1-3cm)
- *Differential:* uses a known reference point to correct for errors (computed at stations and sent to rover) which are then broadcast to the rover using differential techniques. (1-2m)
###### Augmentations:
- systems designed to enhance the performance of (GNSS) by improving accuracy and availability.
- **WAAS:** Satellite-Based Augmentation System covers wide areas, ground stations monitor signals and detect errors, master stations compute corrections and then the geostationary satellites broadcast these corrections to users. (1-2m)
- **LAAS:** Ground-Based Augmentation System (like airport) which sends correction data to users in area using ground based stations. (cm accuracy )
**Assisted GPS:** Mobile Station Based A-GPS, the device  computes position using assistance data (ephemeris, almanac) passed down from cellular networks and reports geographical coordinates back to the network.

###### Remote sensing
- **Reflectometry:**
	- analyze signals from GNSS after they reflect off the Earth's surface.
	- This reflection has key properties that describe several different characteristics and properties it has went through.
	-  Surface roughness, reflectivity, interference patterns.
- **Radio Occultation:**
	- profiles the atmosphere by analyzing GNSS signals as they graze Earths limb.
	- Occulation occurs when a GNSS satellite sets or rises relative to a Low Earth Orbit (LEO) satellite. The signal path passes through successive atmospheric layers  and bends due to atmospheric refraction.
- **Ground based:**
	- delays and distortion in the GNSS signals can be leveraged to derive critical atmospheric parameters.
	- This can either be measured with Zenith Total Delay which provides information about the wet and dry troposphere.
	- or measured by Slant Total Delay (slanted path) to provide more information about atmospheric heterogeneity.

# Geodetic Techniques:
#### VLBI:
- VLBI is a radio interferometry technique that uses multiple widely separated telescopes (baselines of thousands of kilometers) to simulate a single, enormous telescope.
- It looks at compact cosmic sources that are practically fixed and reads in the signals from them.
- The key goal is to achieve extremely high angular resolution, proportional to the baseline length divided by the observing wavelength.
- data from all stations are combined in a correlator.
- Any apparent motion lets us derive EOP from earths orientation like xp yp UT1.
#### DORIS:
- One way doppler system where ground beacons emit signals that are observed by satellites at diff positions to derive the doppler shifted frequencies for accurate orbit determination.
#### SLR:
- Measures the distance between ground stations and satellites using laser pulses.
- SLR retroreflectors have three mutually perpendicular reflective surfaces which ensures the outgoing light is directed back toward the source regardless of the prism's orientation.
- Accounts for earth rotation over instaneous station position (with fluctuations and short term deformations like tides) and regularized station position (averaged over time) and orbital parameters.
#### PRARE:
-  The ground station transmits a coded microwave signal (X/S-band) to the satellite.
- The satellites PRARE system receives the signal, filters it, decodes the data,  sends it back with extra site-specific low-rate information.
- By correlating the transmitted and received signals, PRARE calculates the time delay (for range) and frequency shift (for range-rate).
#### Altimetry
- Its mainly used in understanding and monitoring global sea level rise alongside Studying ice sheet thickness, coastal processes, and inland water bodies.
- The radio waves are sent to the ocean surface which are first reflected as a point reflection then as a cirlcle then as a disc which has a specific curve that it displays in the reciever signal.
- we can infer significant wave height, wind speed, rainfall, floating ice presence, and many others.
- Corrections include:
	- orbit errors
	- instrumental effects
	- ionospheric refraction (Ionized particles)
	- tropospheric refraction both dry and wet which is why we try to estimate water vapor content with radiometer.
	- target surface effects like tides.
- Dynamic Ocean Topography is the deviation of the sea surface height (SSH) from the geoid.
# Gravity missions:
- the satellite orbit is numerically integrated in an inertial reference system to be able to detect the forces that act upon the satellite. however the forces can be gravitational and nongravitational effects
- Computed - Observed residuals help us improve out computed orbit to model more forces.
- We optimize spherical harmonic coefficients to fit this as best as we can and this varies with location and time.
- Long wavelength features include global or regional trends like mantle convection.
- Short wavelength features like mountain ranges and groundwater pumping.
###### CHAMP:
- has High-Low Satellite-to-Satellite Tracking which uses GPS for time and velocity tracking
- Accelerometer to model nongravitational forces
- longterm long wavelength effects
###### Grace:
- LEO
- Uses HL satellite satellite tracking alongside LL of two components 220km apat.
- Accelerometer to estimate nongravitational fores
- microwave length to measure distance
- low wavelength frequency by time variable
###### GOCE:
-  Short wavelength static features
- the segments are 50cm aart and measure changes in all directions
- used ION thrust activations to correct for non gravitational forces

