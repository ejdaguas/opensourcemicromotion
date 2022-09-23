This readme.txt file was last updated on 2022-04-28 by Erika Davidoff. <br>

### GENERAL INFORMATION

Title of Dataset: Micromotion Simulation Device Dataset<br>

Principal Investgator: Jay. C. Sy, PhD. jay.c.sy@rutgers.edu<br>
First Author: Erika D. Aguas, MEng. erika.davidoff@rutgers.edu<br>
Institutiton: Dept of Biomedical Engineering, Rutgers University–New Brunswick<br>
Address: 599 Taylor Road, Piscataway, NJ 08854<br>

Date of data collection: 2019-2022<br>

Funding sources supporting data collection:<br>
GAANN Fellowship in Precision and Personalized Medicine<br>
Rutgers Biotechnology Training Program Fellowship<br>
NJ Commission on Brain Injury Research Fellowship <br>
Busch Biomedical Grant Program<br>

This data is intended to accompany the PLoS One submission "A custom low-cost device for simulating micromotion around implants" (2022). <br>

No restrictions are placed on this dataset.

### DATASET OVERVIEW

#### File list:
backlashdata.csv	&emsp;	Fig 6. Position data extracted from Fig 3 calibration data <br>
calibration_0.90duty.xlsx	&emsp;Fig 3. Calibration data for 10% effective duty<br>
calibration_0.95duty.xlsx	&emsp;Fig 3. Calibration data for 5% effective duty<br>
calibration_0.99duty.xlsx	&emsp;Fig 3. Calibration data for 1% effective duty<br>
calibration_duty.xlsx	&emsp;Fig 3. Summary and figure production for calibration data<br>
calibration_gelvsnogel.csv &emsp;Supplementary Fig. 3, comparing velocity in agarose gel vs without gel<br>
drift.csv		&emsp;Supplementary Fig. 4, position data captured every 10 minutes over 48 hours<br>
PEGDAmap_b0t000.jpg	&emsp;Fig 4. Frame from video of PEGDA-coated gel that was used to create velocity map<br>
PEGDAmap.csv	&emsp;	Fig 4. Matrix used to generate PEGDA velocity map, represents one gel sample.<br>
PEmap_b0t000.jpg		&emsp;Fig 4. Frame from video of PE-coated gel that was used to create velocity map<br>
PEmap.csv	&emsp;Fig 4. Matrix used to generate PE velocity map, represents one gel sample.<br>
PWMoscil.csv		&emsp;Fig 2. Voltage data at PWM chip 1 during device operation. Time step 1/37500<br>
PWMoscil2.csv		&emsp;Fig 2. Voltage data at PWM chip 2 during device operation. Time step 1/37500<br>
PWMoscilArduino.csv	&emsp;Fig 2. Voltage data at Arduino pin 1 during device operation. Time step 1/37500<br>
PWMoscilArduino2.csv	&emsp;Fig 2. Voltage data at Arduino pin 2 during device operation. Time step 1/37500<br>
velocity_PE.csv		&emsp;Fig 5. Average velocity of tissue surrounding PE-coated probes in mm/s<br>
velocityaxis_PE.csv	&emsp;Fig 5. Distance from probe corresponding to the velocities in mm<br>
velocity_PEGDA.csv	&emsp;Fig 5. Average velocity of tissue surrounding PEGDA-coated probes in mm/s<br>
velocityaxis_PEGDA.csv&emsp;	Fig 5. Distance from probe corresponding to the velocities in mm<br>
velocitydata.mat	&emsp;	Fig 5. All Fig 5. data in one MATLAB file<br>

#### Additional related data collected but not included here: 
– Velocity map data for the other 10 PE-coated and 6 PEGDA-coated probes<br>
– JPG images corresponding to all calibration and velocity data<br>

There are no other versions of this data set.

### FILE-SPECIFIC INFORMATION

backlashdata.csv<br>
– Column A: Time point (seconds)<br>
– Colums B-J: Poition of reference feature on device (mm). Three reference features for each frequency (225 Hz B-D, 210 Hz E-G, 200 Hz H-J) are given. Positions in each column are normalized to the mean position of that column, which is set to 0.<br>

calibration_xduty.xlsx<br>
– Kept in XLS format to preserve graphs<br>
– Columns represent position (µm), displacement (µm), and velocity magnitude (µm/s) of device at frequency indicated in column header and effective duty indicated in filename (effective duty = (1-x)*100%)<br>
– Final sheet shows average velocity magnitude per frequency, with standard error<br>

calibration_duty.xlsx<br>
– Compilation of the average velocity magnitude per frequency data from the three tested duties<br>
– This data generated figure 3<br>

calibration_gelvsnogel.csv<br>
– Columns represent frequency + gel status combinations (150-300Hz, either gel or no gel)<br>
– Second row is average of values in the column<br>
– Each value represents the velocity (distance traveled in mm/timestep in seconds) of the test probe from one frame of the video to the next. These veolcities are averaged to produce the data shown in the figure. Videos taken did not all have the same number of frames, so the total number of values per column differs, with a minimum of 177 values.<br>

drift.csv<br>
– Column A: Frame number<br>
– Columns B/C: Time in minute/hour (10 miutes between frames)<br>
– Columns D/E: x and y position of reference point in the frame, in pixels<br>
– Column F: x position normalized to the mean (mean position = 0)<br>
— Column G: x position in µm using 3.0864µm/pixel scaling factor<br>

PEGDAmap.csv, PEmap.csv<br>
– 89x119 double<br>
– Values represent mean velocity magnitude in mm/s<br>
– Largest velocity is 3.66e-5 mm/s, smallest is 6.14e-6 mm/s<br>
– Rows and columns correspond to pixels in the final image. The final image represents 2.6mm in the longer dimension. Each pixel therefore corresponds to ~22µm, which is the scale used to plot the images in figure 4. <br>

PEGDAmap_b0t000.jpg, PEmap_b0t000.jpg<br>
– JPEG images used as overlays over the velocity maps to draw probe locations for figure 4<br>

PWMoscil.csv, PWMoscil2.csv<br>
– 600750 values, double<br>
– Values represent voltage in V measured at each PWM chip. Timestep is 1/37500 seconds<br>

PWMoscilArduino.csv, PWMoscilArduino2.csv<br>
– 300750 values, double<br>
– Values represent voltage in V measured at each Arduino output pin. Timestep is 1/37500 seconds

velocity_PE.csv, velocity_PEGDA.csv<br>
— Each column represents one probe<br>
— Each value represents the mean velocity magnitude (mm/s) a certain distance away from the probe. The distance is in the corresponding matrix position in velocityaxis_PE.csv or velocityaxis_PEGDA.csv<br>
– NaN values represent distances represented by fewer than 20 vectors; this somewhat arbitrary cut-off was used to ensure that there was enough data for each included point to produce a meaningful mean velocity magnitude <br>

velocityaxis_PE.csv, velocityaxis_PEGDA.csv<br>
— These files correspond 1:1 with velocity_PE.csv and velocity_PEGDA.csv<br>
— Each entry is the distance from probe surface (in mm) associated with the corresponding mean velocity magnitude in velocity_PE.csv and velocity_PEGDA.csv<br>

velocitydata.mat<br>
— Combination of the above four documents into one MATLAB file.
