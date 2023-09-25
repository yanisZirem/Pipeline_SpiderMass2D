# T-DAPIA: Two-dimensional Analysis Pipeline for MSI Artificial Intelligence (T-DAPIA)

T-DAPIA is a Python-based Two-dimensional Analysis Pipeline designed for Artificial Intelligence (AI) applications in mass spectrometry imaging (MSI).
This pipeline provides functionality for processing and analyzing MSI data, including generating Total Ion Current (TIC) maps, label maps (based on trained ML model),
calculating label ratios, and visualizing ion images. 
T-DAPIA leverages libraries such as numpy, pandas, matplotlib, pyimzml, scipy, and joblib to perform these tasks.

# Usage

# Generating a TIC Map
A Total Ion Current (TIC) map represents the cumulative intensity of all ions within a specified mass range. 
To generate a TIC map, you can use the generate_tic_map function:
generate_tic_map(imzml_file, mzs_range=(600, 1000), sigma=0.5, new_resolution=4.0)
imzml_file: Path to the imzML file containing the MSI data.
mzs_range: Mass range for filtering ions.
sigma: Standard deviation for Gaussian smoothing.
new_resolution: New spatial resolution after interpolation.

# Generating Label Maps
Label maps (Scoring)
provide spatial distribution information for different labels or classes in MSI data. 
To generate label maps, you can use the generate_label_maps function:

generate_label_maps(imzml_file, model_file, mass_range=(600, 1000), max_intensity_size=4000, sigma=0.0, new_resolution=4.0, real_pixel_threshold=20000)
imzml_file: Path to the imzML file containing the MSI data.
model_file: Path to the trained machine learning model for label prediction.
mass_range: Mass range for filtering ions.
max_intensity_size: Maximum intensity size to consider.
sigma: Standard deviation for Gaussian smoothing.
new_resolution: New spatial resolution after interpolation.
real_pixel_threshold: Threshold for considering real pixels.

#  Calculating Label Ratios
The calculate_label_ratios function calculates the ratios of different labels in the MSI data based on a trained model:
df_ratios = calculate_label_ratios(imzml_file, model_file, mass_range=(600, 1000), max_intensity_size=4000, sigma=0.0, new_resolution=0, real_pixel_threshold=10000)
imzml_file: Path to the imzML file containing the MSI data.
model_file: Path to the trained machine learning model for label prediction.
mass_range: Mass range for filtering ions.
max_intensity_size: Maximum intensity size to consider.
sigma: Standard deviation for Gaussian smoothing.
new_resolution: New spatial resolution after interpolation.
real_pixel_threshold: Threshold for considering real pixels.

#  Generating an Ion Image and Plotting It
To generate an ion image and plot it, use the getionimage_and_plot function:
getionimage_and_plot(imzml_file, mz_value, tol=0.5, z=1, reduce_func=sum, sigma=0.1, zoom_factor=4)
imzml_file: Path to the imzML file containing the MSI data.
mz_value: Desired m/z value for the ion image.
tol: Tolerance for m/z value matching.
z: Ionization charge.
reduce_func: Function to reduce intensities (e.g., sum).
sigma: Standard deviation for Gaussian smoothing.
zoom_factor: Zoom factor for the image.

# Disclaimer
The pipeline is subject to improvements and updates, so make sure to check for the latest version and documentation.
Devalopped by Yanis Zirem 
for more information please contact [yanis.zirem2016@gmail.com]
