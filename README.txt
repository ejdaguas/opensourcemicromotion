This readme.txt file was last updated on 2022-04-28 by Erika Davidoff.

-----------

GENERAL INFORMATION

Title of Dataset: Micromotion Simulation Device Dataset

Principal Investgator: Jay. C. Sy, PhD. jay.c.sy@rutgers.edu
First Author: Erika J. Davidoff, MEng. erika.davidoff@rutgers.edu
Institutiton: Dept of Biomedical Engineering, Rutgers University–New Brunswick
Address: 599 Taylor Road, Piscataway, NJ 08854

Date of data collection: 2019-2022

Funding sources supporting data collection:
GAANN Fellowship in Precision and Personalized Medicine
Rutgers Biotechnology Training Program Fellowship
NJ Commission on Brain Injury Research Fellowship 
Busch Biomedical Grant Program

This data is intended to accompany the PLoS One submission "A custom low-cost device for simulating micromotion around implants" (2022). 

No licenses or restrictions are placed on this dataset.

-----------

DATASET OVERVIEW

File list:
backlashdata.csv		Fig 6. Position data extracted from Fig 3 calibration data
calibration_0.90duty.xlsx	Fig 3. Calibration data for 10% effective duty
calibration_0.95duty.xlsx	Fig 3. Calibration data for 5% effective duty
calibration_0.99duty.xlsx	Fig 3. Calibration data for 1% effective duty
calibration_duty.xlsx	Fig 3. Summary and figure production for calibration data
calibration_gelvsnogel.csv Supplementary Fig. 3, comparing velocity in agarose gel vs without gel
drift.csv		Supplementary Fig. 4, position data captured every 10 minutes over 48 hours
PEGDAmap_b0t000.jpg	Fig 4. Frame from video of PEGDA-coated gel that was used to create velocity map
PEGDAmap.csv		Fig 4. Matrix used to generate PEGDA velocity map, represents one gel sample.
PEmap_b0t000.jpg		Fig 4. Frame from video of PE-coated gel that was used to create velocity map
PEmap.csv		Fig 4. Matrix used to generate PE velocity map, represents one gel sample.
PWMoscil.csv		Fig 2. Voltage data at PWM chip 1 during device operation. Time step 1/37500
PWMoscil2.csv		Fig 2. Voltage data at PWM chip 2 during device operation. Time step 1/37500
PWMoscilArduino.csv	Fig 2. Voltage data at Arduino pin 1 during device operation. Time step 1/37500
PWMoscilArduino2.csv	Fig 2. Voltage data at Arduino pin 2 during device operation. Time step 1/37500
velocity_PE.csv		Fig 5. Average velocity of tissue surrounding PE-coated probes in mm/s
velocityaxis_PE.csv	Fig 5. Distance from probe corresponding to the velocities in mm
velocity_PEGDA.csv	Fig 5. Average velocity of tissue surrounding PEGDA-coated probes in mm/s
velocityaxis_PEGDA.csv	Fig 5. Distance from probe corresponding to the velocities in mm
velocitydata.mat		Fig 5. All Fig 5. data in one MATLAB file

Additional related data collected but not included here: 
– Velocity map data for the other 10 PE-coated and 6 PEGDA-coated probes
– JPG images corresponding to all calibration and velocity data

There are no other versions of this data set.

-----------

FILE-SPECIFIC INFORMATION

backlashdata.csv
– Column A: Time point (seconds)
– Colums B-J: Poition of reference feature on device (mm). Three reference features for each frequency (225 Hz B-D, 210 Hz E-G, 200 Hz H-J) are given. Positions in each column are normalized to the mean position of that column, which is set to 0.

calibration_xduty.xlsx
– Kept in XLS format to preserve graphs
– Columns represent position (µm), displacement (µm), and velocity magnitude (µm/s) of device at frequency indicated in column header and effective duty indicated in filename (effective duty = (1-x)*100%)
– Final sheet shows average velocity magnitude per frequency, with standard error

calibration_duty.xlsx
– Compilation of the average velocity magnitude per frequency data from the three tested duties
– This data generated figure 3

calibration_gelvsnogel.csv
– Columns represent frequency + gel status combinations (150-300Hz, either gel or no gel)
– Second row is average of values in the column
– Each value represents the velocity (distance traveled in mm/timestep in seconds) of the test probe from one frame of the video to the next. These veolcities are averaged to produce the data shown in the figure. Videos taken did not all have the same number of frames, so the total number of values per column differs, with a minimum of 177 values.

drift.csv
– Column A: Frame number
– Columns B/C: Time in minute/hour (10 miutes between frames)
– Columns D/E: x and y position of reference point in the frame, in pixels
– Column F: x position normalized to the mean (mean position = 0)
— Column G: x position in µm using 3.0864µm/pixel scaling factor

PEGDAmap.csv, PEmap.csv
– 89x119 double
– Values represent mean velocity magnitude in mm/s
– Largest velocity is 3.66e-5 mm/s, smallest is 6.14e-6 mm/s
– Rows and columns correspond to pixels in the final image. The final image represents 2.6mm in the longer dimension. Each pixel therefore corresponds to ~22µm, which is the scale used to plot the images in figure 4. 

PEGDAmap_b0t000.jpg, PEmap_b0t000.jpg
– JPEG images used as overlays over the velocity maps to draw probe locations for figure 4

PWMoscil.csv, PWMoscil2.csv
– 600750 values, double
– Values represent voltage in V measured at each PWM chip. Timestep is 1/37500 seconds

PWMoscilArduino.csv, PWMoscilArduino2.csv
– 300750 values, double
– Values represent voltage in V measured at each Arduino output pin. Timestep is 1/37500 seconds

velocity_PE.csv, velocity_PEGDA.csv
— Each column represents one probe
— Each value represents the mean velocity magnitude (mm/s) a certain distance away from the probe. The distance is in the corresponding matrix position in velocityaxis_PE.csv or velocityaxis_PEGDA.csv
– NaN values represent distances represented by fewer than 20 vectors; this somewhat arbitrary cut-off was used to ensure that there was enough data for each included point to produce a meaningful mean velocity magnitude 

velocityaxis_PE.csv, velocityaxis_PEGDA.csv
— These files correspond 1:1 with velocity_PE.csv and velocity_PEGDA.csv
— Each entry is the distance from probe surface (in mm) associated with the corresponding mean velocity magnitude in velocity_PE.csv and velocity_PEGDA.csv

velocitydata.mat
— Combination of the above four documents into one MATLAB file.