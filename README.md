# Star-Data-Analysis
In this project, I have analysed data on stars. The data contained 240 rows and 7 columns. The columns are as follows:
- Temperature (K) - The surface temperature of a star, measured in Kelvin (K).
- Luminosity (L/Lo) -  The luminosity of a star relative to the Sun's luminosity (Lo).
- Radius (R/Ro) - The radius of a star relative to the Sun's radius (R₀).
- Absolute Magnitude (Mv) - A measure of the intrinsic brightness of a star, i.e., how bright the star would appear at a standard distance of 10 parsecs (about 32.6 light years).
- Star Type - Classification of stars based on their spectral characteristics, temperature, and luminosity.
- Star Color - The apparent color of a star, determined primarily by its surface temperature.
- Spectral Class - A classification system that categorizes stars based on their spectra, primarily determined by their surface temperatures.
There were no missiong values in this data. I created a new column on different star categories based on the radius of the star.
This the DAX for the new Star Category column.
Star Category = 
SWITCH(
    TRUE(),
    'stars (2)'[Radius] >= 1000, "Supergiant",
    'stars (2)'[Radius] >= 10, "Giants",
    'stars (2)'[Radius] >= 2, "Subgiants",
    'stars (2)'[Radius] >= 0.1, "Main-Sequence",
    'stars (2)'[Radius] < 0.1, "White Dwarf",
    "Unknown" // Default value if none of the conditions are met
)
