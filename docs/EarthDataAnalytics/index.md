# Earth Data Analytics Projects

This has projects from the
[Earth Analytics 2024](https://github.com/byandell-Tribal/EarthAnalytics_2024)
course.

- [First Map](#first-map)
- [Climate Project 1](#climate-project-1)
- [Species Distribution Project](#species-distribution-project)
- [Redlining Project](#redlining-project)

## First Map

[UW-Madison](https://wisc.edu) is located in Madison, WI.
There are 40k+ students and thousands of faculty and staff,
a top-rated land grant university located along the shores of
Lake Mendota on [ancestral lands of the Ho-Chunk Nation](https://compliance.wisc.edu/land-acknowledgement/).
Here is the
[campus map](https://map.wisc.edu)
and below is an interactive image of the campus area.

<embed type="text/html" src="uwmadison.html" width="600" height="600">

Python code to create this map can be found in
<https://github.com/byandell-Tribal/first-map-template>
as
[first-map.ipynb](https://github.com/byandell-Tribal/first-map-template/blob/main/first-map.ipynb)
See also R code for the same project as
[first-map.Rmd](https://github.com/byandell-Tribal/first-map-template/blob/main/first-map.Rmd).

## Climate Project 1

The python work is in
[7_Portfolio_Post_Write_Post.ipynb](https://github.com/earthlab-education/climate-coding-challenge-byandell/blob/main/7_Portfolio_Post_Write_Post.ipynb).
Additionally, there is an Rmarkdown version in
[Climate_1.Rmd](https://github.com/earthlab-education/climate-coding-challenge-byandell/blob/main/Climate_1.Rmd)
with rendering below.

<embed type="text/html" src="Climate_1.html" width="1200" height="600">

## Species Distribution Project

The python work is in

- [sandhill-crane-species-download.ipynb](https://github.com/earthlab-education/species-distribution-coding-challenge-byandell/blob/main/notebooks/sandhill-crane-species-download.ipynb)
- [siberian-crane-species-download.ipynb](https://github.com/earthlab-education/species-distribution-coding-challenge-byandell/blob/main/notebooks/siberian-crane-species-download.ipynb)

The former (Sandhill Crane) was the original work. My maps are quite similar to
those of
[Nolan Welsh](https://github.com/earthlab-education/species-distribution-coding-challenge-npwelsh/blob/main/notebooks/sandhill-crane-migration-portfolio-post.ipynb),
where he gives an excellent account of this elegent, big bird commonly found 
across North America. My Sandhill Crane migration map is below

<embed type="text/html" src="sandhill-crane-migration.html" width="1200" height="600">

I live within an hour of the
[International Crane Foundation (ICF)](https://savingcranes.org/)
located in
[Baraboo, WI](https://www.google.com/maps/place/International+Crane+Foundation/@43.5471862,-89.7585713,1275m/data=!3m1!1e3!4m14!1m7!3m6!1s0x880741389b381eb1:0x7394b9e281c9cb00!2sInternational+Crane+Foundation!8m2!3d43.5471823!4d-89.755991!16zL20vMDN0djUz!3m5!1s0x880741389b381eb1:0x7394b9e281c9cb00!8m2!3d43.5471823!4d-89.755991!16zL20vMDN0djUz?entry=ttu&g_ep=EgoyMDI0MTExMS4wIKXMDSoASAFQAw%3D%3D).
The executive director is a friend and neighbor here in Madison.
Roughly 50 years ago, I had a
[Watson Fellowship](https://watson.foundation/fellowships/tj),
which enabled me to travel the world for a year.
I spent the second half of my year in the Indian subcontinent.
While in India, I met Paul Spitzer and Ron Sauey at the
[Keoladeo Ghana National Park and Bharatpur Bird Sanctuary](https://www.tourism.rajasthan.gov.in/keoladeo-ghana-national-park.htm).
Ron was the co-founder of ICF with George Archibald.
I later traveled with Paul for several months to Nepal and Ladakh to observe
birds, hoping to see the Black-necked Crane of Tibet (alas, no sighting,
but we were at its winter feeding grounds).
While at Bharapbur, I saw several species of cranes, including the rare
[Siberian Crane]().
I got to watch the 63 birds leave there to migrate north to
China or Russia. That got me curious to view their current (2023) migration,
which is seen below. I learned that the Siberian Crane no longer migrates to
India. Rather, the remainining western populations is a pair in Iran (see
[story](https://osme.org/2023/10/the-story-of-the-last-surviving-wild-siberian-crane-omid-and-roya/#:~:text=The%20Siberian%20Crane%20is%20a,Siberian%20cranes%20in%20the%20wild.)).
You can see in the map below the presence in Iran in January and February, 2023.

<embed type="text/html" src="siberian-crane-migration.html" width="1200" height="600">

I decided to retool the Python code to examine this crane over years, rather
than months in one year. You can see that the Siberian Crane was present in
India through 2002, but not beyond. Note also presence in Iran in 2004 and
2011 onward. [The presence in the Great Lakes Region of the US is no doubt
sighting at the ICF.]

<embed type="text/html" src="siberian-crane-years.html" width="1200" height="600">

The retooling of the 
[Python code for Siberian crane](https://github.com/earthlab-education/species-distribution-coding-challenge-byandell/blob/main/notebooks/siberian-crane-species-download.ipynb)
involved a few changes

- comment out `year == 2023` in call to `occ.download`
- adding `year` to `gdf_montly`
- join by `year` and `month` for `gbif_ecoregion_gdf`
- define function `get_yearly_regional_observations`
- alter `slider` to handle year numbers rather than month names

I did not keep a separate file or workflow for the siberian monthly records
over 2023, but it would be essentially the same as that for the Sandhill Crane.

# Redlining Project

The focus city of my redlining project is Madison, WI.
The goal of my project was to learn how to build a
[landmapy Python package](https://github.com/byandell-envsys/landmapy).
This package is used in the Jupyter notebook
[madison.ipynb](https://github.com/earthlab-education/fundamentals-04-redlining-byandell/blob/main/notebooks/madison.ipynb)
to complete the assignment.
I have not added much context to the report, as my time was consumed with building the package.
Below is the result of decision tree prediction sandwiched between the 
mean NDVI and redlining grades images: 

<embed type="text/html" src="madison_redlining.html" width="1200" height="600">

In addition to this project, I earlier (for the 2024 ESIIL Pre-Summit Sessions) developed
an R package,
[geospatial](https://github.com/byandell-envsys/geospatial),
which has a Shiny app
[redlineApp()](https://github.com/byandell-envsys/geospatial/blob/main/R/redline.R).


