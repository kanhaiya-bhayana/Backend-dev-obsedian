
#Need
## The Need for a Schema Registry

- It takes bytes as an input and publishes them as an output
- Do not perform any data verification

> Producer sends bytes to kafka i.e., the series of 0's and 1's (it doesn't know whether this is a "String or Integer or JSON", and these bytes are redistributed to many applications, and the applications are basically consumer groups.


![[Pasted image 20240330174744.png]]

## Important

- What if the producer sends the bad data?
- What if a field gets renamed?
- What if the data format changes from one day to another?


###############################################################################

- We need data to be self describable
- We need to be able to evolve data without breaking downstream consumers.
- We need schemas ... and a schema registry!



----------------------------------------------------------------------------------
