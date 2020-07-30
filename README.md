**

# Washing machine problem: Fuzzy Logic with *skfuzzy* module
December 01, 2019
*******************************************
A fuzzy control system which models how long it takes the washing machine to wash clothes according to the type of clothes, the dirt, the weight of the clothes and the level of dirt. So you need to consider the type of clothes, dirt, mass of clothes and level of dirtiness, rated between 0 and 10. You use this to know how long it takes the washing machine to wash the clothes between 0 and 20 minutes.
***********************

### **Antecedents (inputs):**

    

 - -type of clothes (tClothes) 
          ◦ Universe: Type of clothes on scale of 0-10 
          ◦ Fuzzy set: silk, cotton
 - - type of dirt (tDirty)
           ◦ Universe: Type of dirt on scale of 0-10
           ◦ Fuzzy set: greasy, non greasy, mix
 - -mass of clothes (mClothes) 
           ◦ Universe: Mass of clothes (in lb (0-10)) 
           ◦ Fuzzy set: Mass of clothes 1-3lb, 4-6lb and 7-10lb
 - -dirtiness of cloths (dClothes) 
           ◦ Universe: Level of dirtiness of cloths in scale(1-10) 
           ◦ Fuzzy set: low, medium, high


### Consequents (Outputs)

 - -washing time (wTime)  • Universe: How long it takes the washing machine to wash the clothes in minutes between 0 and 20?  • Fuzzy
   set: Very short, short, medium, large, very larg
### Rules
 - **IF** tClothes **is** silk **and** tDirty **is** greasy **and** mClothes is 4-6lb **and**
   dClothes **is** medium **THEN** the wTime will be medium
 - **IF** tClothes ***is*** silk **and** tDirty **is** **no** greasy **and** mClothes is 1-3lb **and**
   dClothes **is** low **THEN** the wTime will be very short
 - IF tClothes is silk and tDirty is mix and mClothes is 7-10lb and
   dClothes is high THEN the wTime will be very large
 - IF tClothes is silk and tDirty is greasy and mClothes is 1-3lb and
   dClothes is medium THEN the wTime will be short
 - IF tClothes is silk and tDirty is mix and mClothes is 1-3lb and
   dClothes is high THEN the wTime will be large
 - IF tClothes is silk and tDirty is mix and mClothes is 4-6lb and
   dClothes is high THEN the wTime will be very large
 - IF tClothes is silk and tDirty is greasy and mClothes is 7-10lb and
   dClothes is medium THEN the wTime will be large
 - IF tClothes is silk and tDirty is no greasy and mClothes is 4-6lb and
   dClothes is low THEN the wTime will be very short
 - IF tClothes is silk and tDirty is no greasy and mClothes is 7-10lb
   and dClothes is low THEN the wTime will be short
 - IF tClothes is cotton and tDirty is mix and mClothes is 7-10lb and
   dClothes is high THEN the wTime will be very large
 - IF tClothes is cotton and tDirty is greasy and mClothes is 7-10lb and
   dClothes is medium THEN the wTime will be large
 - IF tClothes is cotton and tDirty is no greasy and mClothes is 1-3lb
   and dClothes is low THEN the wTime will be very short
 - IF tClothes is cotton and tDirty is mix and mClothes is 1-3lb and
   dClothes is high THEN the wTime will be short
 - IF tClothes is cotton and tDirty is mix and mClothes is 4-6lb and
   dClothes is high THEN the wTime will be large

 

 - IF tClothes is cotton and tDirty is greasy and mClothes is 1-3lb and
   dClothes is medium THEN the wTime will be short
 - IF tClothes is cotton and tDirty is greasy and mClothes is 7-10lb and
   dClothes is medium THEN the wTime will be very large
 - IF tClothes is cotton and tDirty is no greasy and mClothes is 7-10lb
   and dClothes is low THEN the wTime will be large
 - IF tClothes is cotton and tDirty is no greasy and mClothes is 4-6lb
   and dClothes is low THEN the wTime will be short

### Usage
**If I tell the controller that I rated:** 

 - the type of clothes as 5
 - the type of dirt as 4
 - the mass of clothes as 9
 - the dirtiness of cloths as 3

 **It would tell you that the washing time will be**:

 - 13.4 minutes