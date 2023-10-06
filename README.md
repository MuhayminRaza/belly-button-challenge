# belly-button-challenge


This challenge required us to build an interactive dashboard to explore the Belly Button Biodiversity dataset. 
The instructions were as follows: 

1. Use the D3 library to read in samples.json from the URL https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.1/14-Interactive-Web-Visualizations/02-Homework/samples.json.

2. Create a horizontal bar chart with a dropdown menu to display the top 10 OTUs found in that individual. Use sample_values as the values for the bar chart. Use otu_ids as the labels for the bar chart. Use otu_labels as the hovertext for the chart.

3. Create a bubble chart that displays each sample. Use otu_ids for the x values. Use sample_values for the y values. Use sample_values for the marker size. Use otu_ids for the marker colors. Use otu_labels for the text values.

4. Display the sample metadata, i.e., an individual's demographic information.

5. Display each key-value pair from the metadata JSON object somewhere on the page.

The following code was written with the help of a TA during office hours: 

function metaData(demographicData){
  let demoData = d3.select('#sample-metadata');
  demoData.html(
     `id: ${demographicData.id} <br> 
   ethnicity: ${demographicData.ethnicity} <br>
   gender: ${demographicData.gender} <br>
   age: ${demographicData.age} <br>
   location: ${demographicData.location} <br>
   bbtype: ${demographicData.bbtype} <br>
   wfreq: ${demographicData.wfreq}`
 )

 var trace1 = {
     x: selectedId.otu_ids,
     y: selectedId.sample_values,
     mode: 'markers',
     marker: {
       size: selectedId.sample_values,
       color: selectedId.otu_ids,
       colorscale : "Earth"
     }
   };
