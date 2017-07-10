Measuring Earth's Axial Title <br> Aubrey Browne <br> DSCI6005 <br> September 2016
----
The goal of this project was to calculate Earth’s axial tilt with a combination Venus’ position data and linear algebra. The axial tilt is the angle between the rotational axis of the planet and the orbital axis.

![](axial_tilt.jpg)

This is a very interesting problem because the tilt of the Earth allows for intelligent life. Without the tilt we would expect there to be extreme and harsh climates which could possibly be inhabitable. Instead, there is  'mild' changes  (the four seasons) throughout the year.

Using the positions of Venus throughout a year timespan and Kepler's laws of planetary motion, I calculated Earth's axial tilt. The concepts used were the law of cosines, Kepler’s third law of planetary motion, and vector geometry methods.

![](Law_of_Cosines1.jpg)
![](kepler-third-law.jpg)

Through the observation of the planets in our solar system astronomers have continued to calculated Earth's axial tilt with higher degrees of accuracy. I used the HORIZONS Web-Interface from JPL and NASA to get a year's worth of data on Venus. After graphing Venus' position in our sky, I found that its' position moved sinusoidally and from this I was able to infer the angle of Earth's axial tilt is 23.77. However, the widely accepted tilt is 25.44 degrees.

To make up for the error, I used vector geometry methods and Kepler's third law of planetary motion. I calculated the distance between Earth and the Sun using Kepler's laws. I was given the distance between Venus and Earth through the HORIZON database. I just needed the distance between the Sun and Venus which I found through the use of the seperation_3d function through astropy. Then using the law of cosines I found the angle between Venus and the Sun in our sky. Then, I took that value and calculated the corrected axial tilt was 23.47 degrees. This result was far closer than my original calculation.

I calculated Earth's axial tilt to be 23.477 degrees. My measurement was only off by 0.04 degrees from the accepted measurement which is an error rate of 0.17%. A few ways to improve my measurement would be to use more data. This could be accomplished through extending the observation time of Venus and/or using observations of additional planets.


PsuedoCode
----
defined a function for the angle correction:  

     solve for the distance between Earth and the Sun (b)  
     b = 1 - 0.01672*np.cos(0.9856*(day - 2))  

     solve for distance between Sun and Venus on a specfic date
     SkyCoord(Sun)
     SkyCoord(Venus)
     then calculate the seperation between the two coordinates (c)
     c = c1.separation_3d(c2).value

     plug into the law of cosine to find angle correction
     arccos(a^2 + c^2 - b^2)/2(ac)

     return distance
