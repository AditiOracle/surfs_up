# surfs_up
**MODULE 9**

**Surfs up Challenge**

**Overview of the analysis:** In this challenge, we are helping in the data analysis for setting up a surf shop and also thinking in the longer term if the shop on Oahu will work well or not.

So for this particular challenge we looked for temperature trends before opening the surf shop. Specifically, temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

**Results:**

- There is no big variation in the temperature of June (Min-64 F and Max 85 F) and December (Min 56 F- max 83 F)
- The business will be big success through the year. Because there is optimum temperature in the Month of June and December for customer to enjoy ice cream.
- He has to maintain the temperature of the freezers in this hot weather because the maximum temperature is varying from (83 F- 85 F) and there are chances of ice cream to lose its consistency.

![JUNE TEAMPERATURE DESCRIPTION:](https://github.com/AditiOracle/surfs_up/blob/main/Resources/June_Temperature.PNG)
![DECEMBER TEAMPERATURE DESCRIPTION:](https://github.com/AditiOracle/surfs_up/blob/main/Resources/December_Temperature.PNG)

**Summary:** As per my analysis, the ice cream business will surely work throughout the year. There is not much variation in the temperatures. The temperature is best in June and also in December to have the ice-cream business and ice-cream in Oahu.

**Two Additional Queries on June and December Weather Data:**
```
#Avg Temp and Avg prcp from each station in the month of December

results=session.query(Measurement.station,func.avg(Measurement.tobs),func.avg(Measurement.prcp)).\

filter(extract(&quot;month&quot;, Measurement.date)==&quot;12&quot;).\

group\_by(Measurement.station).all()

Dec\_Avg\_temp\_prcp\_station=pd.DataFrame(results)

Dec\_Avg\_temp\_prcp\_station.columns=[&quot;Station&quot;,&quot;Avg\_Temperature&quot;,&quot;Avg\_Precipitation&quot;]

Dec\_Avg\_temp\_prcp\_station
```

```
#Avg Temp and Avg prcp from each station in the month of June

results=session.query(Measurement.station,func.avg(Measurement.tobs),func.avg(Measurement.prcp)).\

filter(extract(&quot;month&quot;, Measurement.date)==&quot;06&quot;).\

group\_by(Measurement.station).all()

June\_Avg\_temp\_prcp\_station=pd.DataFrame(results)

June\_Avg\_temp\_prcp\_station.columns=[&quot;Station&quot;,&quot;Avg\_Temperature&quot;,&quot;Avg\_Precipitation&quot;]

June\_Avg\_temp\_prcp\_station
```

```
#DataFrame from the list of precipitations for the month of June

results=session.query(Measurement.date,Measurement.prcp).filter(extract(&quot;month&quot;, Measurement.date)==&quot;06&quot;).all()

df\_June\_prcp=pd.DataFrame(results)

df\_June\_prcp.columns=[&quot;Date&quot;,&quot;June\_prcp&quot;]

df\_June\_prcp
```
```
#summary statistics for the June precipitation DataFrame

df\_June\_prcp.describe()
```

```
#DataFrame from the list of precipitations for the month of December

results=session.query(Measurement.date,Measurement.prcp).filter(extract(&quot;month&quot;, Measurement.date)==&quot;12&quot;).all()

df\_Dec\_prcp=pd.DataFrame(results)

df\_Dec\_prcp.columns=[&quot;Date&quot;,&quot;Dec\_prcp&quot;]

df\_Dec\_prcp
```
```
#summary statistics for the Decemeber precipitation DataFrame
df\_Dec\_prcp.describe()
```
