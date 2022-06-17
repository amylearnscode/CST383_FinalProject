# CST383_FinalProject
Gun Violence and Moon Phase Analysis
Jerome Ortega, Amy Gonzales, Christopher Bray, Nathan Jobes


We took an in depth look into the gun violence dataset. We decided to attempt to determine if moon phases had any correlation with incidences of gun violence. We thought if we could predict this with any accuracy then it would imply a relationship between deviant behavior and the phase of the moon. We also decided to attempt to predict the number of casualties based on the moon phase.

The data we used can be found at: https://github.com/jamesqo/gun-violence-data. We utilized SciKit in this project and imported libraries such as re, math, sklearn.neighbors, and sklearn.preprocessing. The dataset included an incident ID, the date of occurence, the state of the shooting with city or county, number of killed, number of injured, and information about the guns used in the attack. It also provided data regarding the participants in the attack such as gender, age, name, and whether they were victims or suspects. Due to the inconsistencies in the data set, the fields we used for our experiment were limited to date, state, number of people killed and number of people injured. We also used feature engineering, such as one hot encoded state values. 

On closer inspection of the data, guns_involved had a lot of NaN values and inconsistencies including guns seized after the crime, and incidents occurring in a gun store, or in a residence where guns were hoarded. We found that the metric did not include police weapons involved, making this metric unreliable. For example, two incidents could be reported with one gun involved, but one was a man shooting at an officer. The other could be a man with a gun, in a standoff with 40 police officers. Our attempt to filter the data failed as the perpetrator is not always listed as a participant in the data.
We used the logic found at Calculate the Moon Phase to assist with calculating the moon phases and decided to group the phases into their 8 major groups. We coded a function that calculated the moon phases and added this column to our dataset. We made a function to aid in anomaly detection of incidents that could be classified as "raid" data entries. We then created data frames that contain only shootings that are classified as mass shootings and mass casualty events. 

For our models, we primarily focused on using the n_killed and n_injured and the state to predict the moon_phase. We utilized a blind guess to estimate a baseline value for the moon phases, and fitted a KneighborsClassifier model, and a KneighborsRegressor model.

Our results imply no correlation between the moon phase and shooting incidents. This is consistent with other research, according to a Healthline article, which states that the moon phases do not cause shifts in mental health or a propensity towards violence.Future research for this topic may include if humans are affected by the changing of the seasons, causing higher rates of violence in certain months or near the holidays. The healthline article indicates that moon phases can affect sleep, cardiovascular health, and certain mental health disorders such as anxiety and depression, so further study in this area could be useful also.


References

Jamesqo. (2018, Apr 24) Gun Violence Data. Github. https://github.com/jamesqo/gun-violence-data

Stanborough, R. (2020, Sept 9.) How Does a Full Moon Affect Our Physical and Mental Well-Being? Healthline. https://www.healthline.com/health/full-moon-effects. 

Subsystems. (2017) Calculate the Moon Phase. Subsystems.US. https://www.subsystems.us/uploads/9/8/9/4/98948044/moonphase.pdf


