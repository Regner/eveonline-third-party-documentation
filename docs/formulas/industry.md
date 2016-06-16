# Industry

## Research Multipliers
<table border="1">
    <tbody>
        <tr>
            <td>Blueprint Level</td>
            <td>Multiplier</td>
        </tr>
        <tr>
            <td>1</td>
            <td>1</td>
        </tr>
        <tr>
            <td>2</td>
            <td>29 / 21.0</td>
        </tr>
        <tr>
            <td>3</td>
            <td>23 / 7.0</td>
        </tr>
        <tr>
            <td>4</td>
            <td>39 / 5.0</td>
        </tr>
        <tr>
            <td>5</td>
            <td>278 / 15.0</td>
        </tr>
        <tr>
            <td>6</td>
            <td>928 / 21.0</td>
        </tr>
        <tr>
            <td>7</td>
            <td>2200 / 21.0</td>
        </tr>
        <tr>
            <td>8</td>
            <td>5251 / 21.0</td>
        </tr>
        <tr>
            <td>9</td>
            <td>4163 / 7.0</td>
        </tr>
        <tr>
            <td>10</td>
            <td>29660 / 21.0</td>
        </tr>
    </tbody>
</table>

## Planetary Interaction Program Chart
```c#
int[] CalculateExtractorValues() {

    //Inputs - these are set from the API results.
   //Note that all times are in seconds.
   int duration = 171000; //1d 23h 30m; from API expiryTime-installTime
   int cycleTime = 30*60; //30 minutes, value from API cycleTime * 60
   int quantityPerCycle = 6965;
   
   //These constants are the defaults in dgmAttributeTypes. They may change.   
   const float decayFactor = 0.012f; //Dogma attribute 1683 for this pin typeID
   const float noiseFactor = 0.8f;   //Dogma attribute 1687 for this pin typeID
           
    int numIterations = duration / cycleTime;
   float barWidth = cycleTime / 900f;
   int[] values = new int[numIterations];
    for (int i = 0; i < numIterations; i++)
   {
       float t = (i + 0.5f)*barWidth;
       float decayValue = quantityPerCycle/(1 + t * decayFactor);
       double phaseShift = Math.Pow(quantityPerCycle, 0.7f);
   
          double sinA = Math.Cos(phaseShift + t*(1/12f));
       double sinB = Math.Cos(phaseShift/2 + t*0.2f);
       double sinC = Math.Cos(t*0.5f);
   
          double sinStuff = (sinA + sinB + sinC)/3;
       sinStuff = Math.Max(sinStuff, 0);
   
          double barHeight = decayValue*(1 + noiseFactor*sinStuff);
   
          values[i] = (int) (barWidth*barHeight);
   }
   return values;
}
```