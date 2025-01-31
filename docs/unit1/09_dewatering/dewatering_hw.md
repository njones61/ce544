# Homework - Construction Dewatering

In this exercise, we will design a dewatering trench using the Dupuit analytical solution and we will design a 
dewatering system for the Provo City Center Temple excavation site using a Python script in a Google Colab notebook.

## Exercise 1 - Dewatering Trench Design

The Los Pollos Hermanos Corporation is planning to build a new manufacturing facility near the Rio Grande River in the outskirts of Albuquerque, New Mexico. The facility will include a hermetically-sealed underground unit with state-of-the-art ventillation and chemical-processing equipment. In order to dewater the site during construction and to ensure that it stays dry while in operation, the company decides to build a french drain between the river and excavation as follows:

![trench.png](images/trench.png)

A pump will be attached to the drain and the water will be returned to the river. Calculate what capacity will be required (gpm) for the pump. To simplify your calculations, assume that there is a lower permeability layer at the elevation corresponding to the bottom of the excavation. Use a spreadsheet for your calculations.

!!! Note
    Be careful with the values for Ho and HD in the equation. They should be measured from the datum, which is the bottom of the trench. Don't use the elevations.

## Exercise 2 - Provo City Center Temple Dewatering

The Provo City Center Temple is a temple of The Church of Jesus Christ of Latter-day Saints in Provo, Utah. The 
temple is located on the site of the former Provo Tabernacle, which was destroyed by fire in December 2010, leaving 
only the outer brick facade intact.

![tabernacle_fire.jpg](images/tabernacle_fire.jpg)

The Church of Jesus Christ of Latter-day Saints announced during the October 2011 general conference that the structure 
woud be rebuilt as the 
Provo City Center Temple. This is an architect's rendering of the planned temple:

![temple.jpg](images/temple.jpg)

The engineers in charge of the reconstruction faced a difficult task. As a temple, the structure would need to have a basement to house a baptismal font. Furthermore, there was a need to ensure that the reconstructed building is supported by an adequate, modern foundation. This would have to be done without damaging the fragile brick facade. To this they designed an elaborate system of piles:

![excavation.jpg](images/excavation.jpg)

The excavation went down to a depth of 30 feet below the original ground surface. This presented another challenge because the water table in this region is shallow. In order to accomplish the construction, the site had to be dewatered. This is typically accomplished using a set of shallow wells where each well lowers the water table and creates a "cone of depression" surrounding the well. Multiples wells provide a combined effect resulting in an aggregate zone of drawdown.

Our objective in this exercise is to design a dewatering system using the Google Colab notebook we used for the 
in-class exercise. The notebook is available at the following link:

Python starter file: <a href="https://colab.research.google.
com/github/njones61/ce544/blob/main/docs/unit1/09_dewatering/dewatering.ipynb" target="_blank"><img src="https://colab.
research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Before starting, download the following GEOJSON file:

GEOJSON File: [temple.geojson](temple.geojson)

This represents the footprint of the excavation:

![temple_polygon.png](images/temple_polygon.png)

Assume the following parameters for the problem:


| Parameter | Value | units  |
|----------|-------|--------|
| $k$      | 0.007 | cm/sec |
| $H$      | 30    | m      |
| $R$      | 400   | ft     |
| Design H | 25    | ft     |
| $Q$      | 0.025 | m³/s   |


(a)  Manual Placement

Design a dewatering system under three conditions: 2 wells, 4 wells, and 6 wells. In each case, 
assume 
that the you can only place the wells outside of the temple footprint. You should change the location of the wells and the total pumping rate.

Save a screen copy of each of each of your designs. Open a Word document and write a short section for each of your three designs (including the screen shots) and discuss the results. Indicate which of the three designs you would suggest using for the actual project.

(b) Automated Placement

In the second part of the notebook, use the algorithm that automatically places a line of wells around the perimeter of 
the excavation based on an offset distance from the excavation boundary and a specified well spacing. Use an offset 
of 20 ft. Experiment with the well spacing. Make a plot of total pumping rate vs well spacing and include in your 
report. Discuss the results. 

## Submission

Make a zip archive of your spreadsheet for part 1 and your Word document for part 2. Submit the zip archive on Learning Suite after we grade it together in class.

## Grading Rubric

Self-grade your assignment using the following rubric. Enter your points in the "Submission notes" section for the assignment on Learning Suite when you upload your file. You can use fractional points if you like (e.g. 2.5).

| Criteria                                    | Points |
|---------------------------------------------|:------:|
| Completed on time and all or mostly correct |   3    |
| Completed more than half of assignment      |   2    |
| Made an effort                              |   1    |
| Did nothing                                 |   0    |