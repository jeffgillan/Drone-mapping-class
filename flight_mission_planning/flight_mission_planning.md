
<figure markdown>
  ![Image title](images/mission_planning.png){ width="600" }
  <figcaption> </figcaption>
</figure>

<br/> 
This module will cover the basics of how to collect drone imagery for photographic mapping purposes. The topics include:

* Physical camera characteristics

* Aerial Imagery Scale

* Principles of Stereo Photography

* Autonomous Mission Planning

<br/>
____

## Camera Characteristics

### Focal Length & Field of View
Inside the camera, the **Focal Length** is the distance from the lens to the sensor plane (usually reported in mm)
<br/>

<figure markdown>
  ![Image title](images/focal_length.png){ width="750" }
  <figcaption> </figcaption>
</figure>

<br/>

The **camera field of view (FOV)**, also called the angle of view, is the extent of the observable world that can be seen at any give moment. FOV is typically reported in degrees and can vary greatly between lens and camera types. 
<br/>
<br/>
Typically a camera with a longer focal length will have a narrower FOV and a camera with a shorter focal length will have a wider FOV. Drone cameras often have a fairly wide FOV because they are meant
to capture landscapes. 
<br/>
<br/>
The graphic below shows the relationship between focal length and FOV. Highlighted is the DJI Phantom 4 multi-rotor drone. 


<figure markdown>
  ![Image title](images/focal_length2.png){ width="600" }
  <figcaption> </figcaption>
</figure>

### Sensor Array

Digital cameras have a **sensor array** of millions of tiny photosites (corresponding to pixels) that are each sensitive to light. The physical size (width and height in mm) as well as
the number of photosites can vary between sensors. 
<br/>
<br/>
The graphic below shows the sensor array of the Phantom 4 camera. Multiplying the number of photosites (pixels) wide by the number of photosites
high will tell you the total number of photosites for the array. In our example, the camera has 19.9 million pixels, which are also called megapixels. 

<figure markdown>
  ![Image title](images/sensor_array.png){ width="600" }
  <figcaption>Sensor Array</figcaption>
</figure>
<br/>
____
## Aerial Imagery Scale
In traditional aerial photography, **scale** was defined as _the ratio of the distance between two points on an image to the actual distance between the same two points on the ground_.
Scale was generally reported as _1:25,000_ or similar. So if I had a printed aerial photograph and measured the distance between two objects to be 0.25 inches and the scale was 1:25,000,
the real world distance between the objects would be 6250 inches (0.25 x 25,000) or 520.8 feet. 
<br/>
<br/>
However, with the advent of fully digital aerial photography workflows and the computer screen being the primary tool for viewing imagery, the traditional concept of reporting scale is less useful. 
<br/>
<br/>
When it comes to drone imagery scale, the two important concepts to understand are **image footprint** and **ground sampling distance**.  
<br/>

**Image Footprint** is the rectangular ground area that is captured by a camera exposure. 

**Ground Sampling Distance (GSD)** is the width of area on the ground that is captured by one pixel. It is also commonly referred to as _pixel size_ or _spatial resolution_.
For example, a pixel that captures an area of 2 x 2 cm (4 cm^2^) is said to have a GSD of 2 cm. 
<br/><br/>

<figure markdown>
  ![Image title](images/gsd_footprint.png){ width="700" }
  <figcaption> </figcaption>
</figure>

<br/><br/>
As a drone camera gets higher in the sky (further away from the ground), the image footprint and GSD get larger.
<br/>
<figure markdown>
  ![Image title](images/combined_scale2.gif){ width="800" }
  <figcaption> </figcaption>
</figure>


We can calculate the image footprint and GSD with simple formulas that include the camera physical characteristics and flying height. 

??? Tip "Image Footprint and GSD Calculator"

    [Pix4D](https://www.pix4d.com/){target=_blank} has a nice [GSD calculator tool]([https://support.pix4d.com/hc/en-us/articles/202560249-TOOLS-GSD-calculator]      (https://s3.amazonaws.com/mics.pix4d.com/KB/documents/Pix4D_GSD_Calculator.xlsx)){target=_blank} to calculate image dimensions and pixel ground sampling distance based on your drone specs
    <figure markdown>
     ![Image title](images/gsd_calculator.png){ width="700" }
      <figcaption> </figcaption>
    </figure>
<br/>
Check out this video which describes how to calculate GSD of aerial images
<iframe width="560" height="315" src="https://www.youtube.com/embed/nUFxmecRCec" title="Scale and Digital Aerial Imagery" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
<br/><br/>
____

## Stereo Aerial Photography

Photographic mapping from drones requires overlapping imagery. That is, as the drone is flying and taking pictures, the image footprints should overlap. Overlap is usually reported as a percentage (%). **Forward overlap** is the overlap % from successive image footprints. **Side overlap** is the overlap % from adjacent flight lines. 

<figure markdown>
  ![Image title](images/stereo_imagery.png){ width="350" }
  <figcaption> </figcaption>
</figure>

For robust photogrammetry, it is recommended to have **forward overlap of 70%-85%** and **side overlap of 70%-80%**. But these are not hard and fast rules, just recommendations. Optimal overlap will differ depending on the landscape you are imaging and your goal for your imagery products. 


<figure markdown>
  ![Image title](images/Forward_overlap.gif){ width="550" }
  <figcaption> </figcaption>
</figure>
<br/><br/>
Footprint overlap means that any given location on the ground is being imaged from multiple perspectives. In the example graphic below, the shrub is being imaged from 6 different perpective views.  

<figure markdown>
  ![Image title](images/six_views.png){ width="450" }
  <figcaption> </figcaption>
</figure>

<br/><br/>
____
## Autonomous Mission Planning

The most efficient way to collect overlapping drone imagery of a landscape is to plan and execute an **autonomous flight plan**. Nearly all modern drones have software applications that empower you program the drone to capture imagery of an area interest - all automatically! 

Please check out the following video for an example of autonomous mission planning. All autonomous planning and flying apps will be slightly different from each other, but the basics are generally universal. It can be as simple as tapping a bounding box, selecting a few user parameters, and launching the drone!  

<iframe width="560" height="315" src="https://www.youtube.com/embed/XoPV-eT-1Ds" title="Ultimate Pix4D tutorial 3D mapping" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<br/>

Autonomous planning and flying apps generally have a suite of user-defined parameters that enable you to customize your flight. These parameters include:

* A box or polygon designating the area to be imaged

* Flying height (m) 

* Ground sampling distance (cm) 

* Forward overlap (%) and side overlap (%)

* Flying speed (m/s)

* Gimbal angle 

Based on the user-defined parameters, the mapping software will compute the following:

* Exact flying route including the number and spacing of flight lines

* Timing between exposures



<figure markdown>
  ![Image title](images/planned_mission.png){ width="350" }
  <figcaption> </figcaption>
</figure>


<figure markdown>
  ![Image title](images/exposure_stations.png){ width="500" }
  <figcaption> </figcaption>
</figure>

??? Tip "Calculate Number of Images per Flight Line"

    <figure markdown>
     ![Image title](images/images_per_line.png){ width="500" }
      <figcaption> </figcaption>
    </figure>


??? Tip "Calculate Number of Flight Lines for a Flight Area"

    <figure markdown>
     ![Image title](images/flight_lines.png){ width="500" }
      <figcaption> </figcaption>
    </figure>


<figure markdown>
  ![Image title](images/controller_screenshot1.png){ width="700" }
  <figcaption> </figcaption>
</figure>

<figure markdown>
  ![Image title](images/controller_screenshot2.png){ width="700" }
  <figcaption> </figcaption>
</figure>

### Double v Single Grid

**Double Grid Advantages:**

Better photographic coverage leading to better 3D modeling
<br/>
<br/>

**Double Grid Disadvantages:** 

Longer flight times; larger datasets that take longer to process

  ![Image title](images/single_grid.png){ width="285" } ![Image title](images/double_grid.png){ width="350" }

### Oblique Imagery

Aerial mapping is typically vertical (nadir) but oblique images can also be used in photogrammetry.
The addition of oblique images ca improve photogrammetry solutions and improve 3D point clouds at the base of vertical objects

<figure markdown>
  ![Image title](images/nadir_oblique.png){ width="300" }
  <figcaption> </figcaption>
</figure>


<figure markdown>
  ![Image title](images/nadir_plus_oblique.png){ width="600" }
  <figcaption> </figcaption>
</figure>

### GSD Recommendations
 Features of interest should drive the optimal GSD; detecting (and 3D modeling) small objects requires finer GSD; Coarser GSD will lead to coarser 3D modeling


<figure markdown>
  ![Image title](images/GSD_recommendations.png){ width="700" }
  <figcaption> </figcaption>
</figure>
<br/><br/>

### Mission planning Tips

* Collect imagery with pre-programmed autonomous flights. Don’t try to collect imagery with manual flying! 

* Make your flight areas into simple polygons like rectangles. Don’t draw complicated flight areas.

* Make the flight polygon bigger than your area of interest by 10-15%. The periphery of imagery products are often of less quality.

* Small alterations to flying height and polygon size can make a big difference in how long the total mission takes 

* Always plan flights around quantity and endurance of your flight batteries
<br/><br/>
___
## Camera Settings

### Exposure Triangle
<figure markdown>
  ![Image title](images/holy_trinity.png){ width="700" }
  <figcaption> </figcaption>
</figure>



<figure markdown>
  ![Image title](images/motion_blur.png){ width="700" }
  <figcaption> </figcaption>
</figure>

### White Balance

White balance: never use automatic white balance! Images will have different hues. Set camera to 'sunny' or 'cloudy'

<figure markdown>
  ![Image title](images/white_balance.png){ width="700" }
  <figcaption> </figcaption>
</figure>

<iframe width="560" height="315" src="https://www.youtube.com/embed/bTIgjjeYtWY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
