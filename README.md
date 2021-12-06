# Perception Exercises

## LiDAR

### Terms

* Time of Flight (ToF)

Most common LiDAR sensor is "pulsed LiDAR" - laser emitting short bursts and a reciever.  When laser hits object, a fraction of the light is refracted back to the reciever.  Based on Time of Flight, the range (R) can be found with this equation:

$R = \frac{1}{2n} \cdot c\Delta t$

$c$ - speed of light in a vaccum

$n$ - index of refraction for substance laser is traveling throught (air = 1.0)

at 2.9

### Terms

Terms and Symbols

In this section, you will find a list of abbreviations and technical expressions used in the lesson. For further details and an in-depth explanation, please refer to the respective sections.

    LiDAR : Light Detection And Ranging.
    Range : Straight-line distance measured between sensor and obstacle.
    Spatial resolution : Measure of the smallest object that can be resolved by the sensor.
    Object classification : Sorting of objects into groups with each group having its own characteristic properties (e.g. vehicles, pedestrians).
    Package : Physical dimensions of a technical device (e.g. the housing of a sensor).
    ToF : Time-of-Flight
    MEMS : Micro-Electro-Mechanical Systems
    FMCW : Frequency-modulated continuous wave
    FOV : Field of view
    Homogeneous coordinates : Mathematical concept that allows operations such as translation, rotation, scaling and perspective projection to be implemented as matrix operations.

Equations

Range equation that delivers the distance to a target:

R=12n⋅cΔt R = \frac{1}{2n}\cdot c \Delta t R=2n1​⋅cΔt

The range RRR is based on the speed of light ccc, the time between light emission and reception ttt and the refractive index nnn of the medium through which the light propagates.

LiDAR equation which describes the relationship between the power at the receiver and various characteristics of the technical setup and its physical surroundings:

P(R)=P0⋅ρ⋅A0π⋅R2⋅η0⋅e−2γR P(R) = P_0\cdot \rho \cdot \frac{A_0}{\pi \cdot R^2}\cdot \eta_0 \cdot e^{-2\gamma R} P(R)=P0​⋅ρ⋅π⋅R2A0​​⋅η0​⋅e−2γR

    P(R)P(R)P(R) : power received
    P0P_0P0​ : peak power transmitted
    ρ\rhoρ : target reflectivity
    A0A_0A0​ : receiver aperture area
    η0\eta_0η0​ : transmission coefficient
    γ\gammaγ : atmospheric extinction coefficient

Light propagation angle for optical phase arrays:

    α\alphaα : Direction into which the light wave is deflected
    λ\lambdaλ : Wavelength of the light
    Φ\PhiΦ : Phase difference between the emitters
    ddd : Spatial difference between the emitters

Converting xxx, yyy and zzz from yaw, pitch and roll angles:

x=rP⋅cosαP⋅cosβP x = r_P \cdot \cos{\alpha_P} \cdot \cos{\beta_P} x=rP​⋅cosαP​⋅cosβP​

y=rP⋅sinαP⋅cosβP y = r_P \cdot \sin{\alpha_P} \cdot \cos{\beta_P} y=rP​⋅sinαP​⋅cosβP​

x=rP⋅sinβP x = r_P \cdot \sin{\beta_P} x=rP​⋅sinβP​

    α\alphaα : Yaw angle
    β\betaβ : Pitch angle

Extrinsic calibration matrix:

[R3x3T3x101x31] \begin{bmatrix} R_{3x3} & T_{3x1} \\ 0_{1x3} & 1 \end{bmatrix} [R3x3​01x3​​T3x1​1​]

The matrix RRR describes the rotation of the sensor around its three coordinate axes in relation to the superior coordinate system (e.g. the vehicle) while the vector TTT denotes the relative center of the coordinate system.



# Sensor Fusion Exercises

This repo contains the code for demos, exercises, and exercise solutions.

This repository organizes the code by the lessons that they are used in. Each set of code is located in their respective lessons, except for the primary `basic_loop.py` file that can run each exercise.

Please note that certain instructions for each exercise are only provided within the Udacity classroom.

## Example:
All lesson 1 files are in `/lesson-1-lidar-sensor/`.

This directory contains: `examples`, `exercises/starter`, and `exercises/solution`.

## Environment

Udacity students can make use of the pre-configured workspace environment within the classroom. Alternatively, you can create an environment using the `requirements.txt` file included in this repository, using a command like `pip install -r requirements.txt` if you have pip installed, or creating an Anaconda environment in similar fashion.

### Waymo Open Dataset Reader
The Waymo Open Dataset Reader is a very convenient toolbox that allows you to access sequences from the Waymo Open Dataset without the need of installing all of the heavy-weight dependencies that come along with the official toolbox. The installation instructions can be found in `tools/waymo_reader/README.md`. 

### Waymo Open Dataset Files
This course makes use of three different sequences to illustrate the concepts of object detection and tracking. These are: 
- Sequence 1 : `training_segment-1005081002024129653_5313_150_5333_150_with_camera_labels.tfrecord`
- Sequence 2 : `training_segment-10072231702153043603_5725_000_5745_000_with_camera_labels.tfrecord`
- Sequence 3 : `training_segment-10963653239323173269_1924_000_1944_000_with_camera_labels.tfrecord`

To download these files, you will have to register with Waymo Open Dataset first: [Open Dataset – Waymo](https://waymo.com/open/terms), if you have not already, making sure to note "Udacity" as your institution.

Once you have done so, please [click here](https://console.cloud.google.com/storage/browser/waymo_open_dataset_v_1_2_0_individual_files) to access the Google Cloud Container that holds all the sequences. Once you have been cleared for access by Waymo (which might take up to 48 hours), you can download the individual sequences. 

The sequences listed above can be found in the folder "training". Please download them and put the `tfrecord`-files into the `dataset` folder within the repository.
