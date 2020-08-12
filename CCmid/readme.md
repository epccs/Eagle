CCmid

Constant currrent source based on AL8805W5-7 for LED or other uses. 

https://oshpark.com/shared_projects/9gUEmC1T

The alternat input of my control boards is for solar power, which acts as a constant current source. To charge from a regulated voltage source, the power needs to be converted through a CC source that is within the batteries charge ratting (e.g., <1/10 C, which is longer than 10 hour charging time) through the alternat input of on one of my boards. The alternat input will switch the CC source on and off, so a load dump needs to be handled with a TVS. 

Note: the lack of TVS on the Sparkfun boards is likely causing them problmes.
