## CorGAT-tracker

Welcome to **CorGAT-tracker** a [Shiny](https://shiny.rstudio.com/) based dashboard for the mapping of SARS-CoV-2 lineages, and mutations of concern (MOC) in space and time in an interactive form.  
This app facilitates the genomic surveillance of SARS-CoV-2 by reporting the prevalence of SARS-CoV-2 Pango lineages and specific mutations (known as Mutations of Concern or MOC) in the spike glycoprotein in different countries over time. To enable a more efficient tracking of emerging lineages, in **CorGAT-tracker** Pango lineage annotations are augmented by reporting the list of MOC that are observed in a genome, but are not specific to a lineage. We call these augmented annotations Lineages+ (see below for a more detailed explanation).  
CorGAT-tracker incorporates data from more than 50 countries, and a total of more than 1.5M genomes deposited in the [GISAID](https://www.gisaid.org/) database.

The dashboard is composed of three different tab/panels each providing a different graphical representation of the data. The behaviour of each plot can be tweaked by the user by adjusting the parameters in the control panel at the bottom of the page.  
A more detailed description of plots and parameters is reported below.

### Plots panels

* ***Barplots panel***  
Barplots are used to represent the total number of SARS-CoV-2 genomes sequenced on a weekly basis in different countries. Three different barplots are displayed and their data are stratified by 1) Pango Lineages, 2) Lineages+ (see below) and 3) MOC Mutations respectively. To keep the visualization compact only the top 5 most abundant Lineages/Lineages+ and the 10 most numerous Mutations are represented. Remaining Lineages, Lineages+ or Mutations are aggregated under *Others*.  
* ***Pie charts panel***  
Three pie charts are used to illustrate the cumulative prevalence of SARS-CoV-2 Lineages, Lineages+ and Mutations in a user-selected interval of time. Similar to barplots only the top 5 most-abundant Lineages/Lineages+ and the 10 most numerous Mutations are represented, while everything else is collapsed under *Others*.  
* ***Scatterplot panel***  
Scatterplots are used to represent the number of genomic sequences associated with a user-selected Lineage or Mutation, in time (week, x axis). To facilitate the comparison, the total number of genomes not associated with the selected Lineage/Mutation is also displayed. Only Lineages and Mutations shown in the barplot and/or pie chart panel can be selected for a scatterplot, meaning that, for any selection of country and time, only the top 5 most prevalent individual Lineages and the 10 most numerous Mutations can be individually represented, all the remaining Lineages/Mutations, can still be visualized but only in a collapsed form under *Others*.

### Control and customization of the plots

Users can interact with **CorGAT-tracker** by means of the set of widgets under the main plot area. These include:  
* The ***Country*** drop down menu, which allows to select the country of origin of the data to be visualized. Default is Italy.  
* The ***Weeks range*** slider, which allows the selection of the interval of  time to be displayed. Intervals of time are computed in the form of non-overlapped windows of 7 days (or weeks if you prefer) starting from 2019-12-30 the reported date of isolation of the first SARS-CoV-2 genomic sequence. This widget defaults to the entire frame of time included in the latest version of the analysis (week 1 to current week).
* The ***Min number of genomes (Lineages)*** radio buttons, which enables the user to select a lower bound for the numerosity required to a Lineage to be represented in the plots. Only Lineages surpassing this minimum threshold will be represented. Please be aware, irrespective of the selection, **CorGAT-tracker** is configured to allow the visualization of a maximum of 5 Lineages at every time-point. Only the 5 most numerous Lineages will be shown by default, remaining Lineages are collapsed under *Others*. Default threshold for this widget is 100.
* The ***Min number of genomes (Lineages+)*** radio buttons, which enables the user to select a lower bound for the numerosity required for a Lineage+ to be represented in the plots. Only Lineages+ surpassing this minimum threshold will be represented. In **CorGAT-tracker** a Lineage+ is defined as a collection of genomes assigned to a Pango lineage which carry one or more Mutations of Concern in the spike glycoprotein that are not typical of that lineage (e.g. B.1.1.7+L18F). Please be aware, irrespective of the selection, **CorGAT-tracker** is configured to allow the visualization of a maximum of 5 Lineages+ at every time-point. Only the 5 most numerous Lineages+ will be shown by default, the remaining Lineages+ are collapsed under *Others*. Defaults to 15.
* The ***Lineage*** drop down menu allows the user to select a Lineage of interest to visualize in the scatter-plot. This widget is generated dynamically based on the current user selection. Please be aware that Lineages available for this type of plot might change and might not be consistent across different countries or between different intervals of time. No default value.
* The ***Mutation*** drop down menu allows the user to select a Mutation of interest to be represented in a scatter-plot. This widget is generated dynamically based on the current user selection. Please be aware, irrespective of the selection, **CorGAT-tracker** is configured to allow the visualization of a maximum of 10 Mutations at every time point. Only the 10 most abundant Mutations will be shown by default, remaining Mutations are collapsed under *Others*. Since the widget is generated in a dynamic manner, Mutations available for the scatter-plot might change and might not be consistent across different countries or between different intervals of time. No default value.

#### Please be aware that to present the user with a more meaningful and compact representation, CorGAT-tracker was designed explicitly to show only the five most numerous Lineages/Lineages+ for any selection performed by the user. The category *Others* is used to collapse all the Lineages/Lineages+ that do not pass this threshold (see above, *Min number of genomes (Lineages)* and *Min number of genomes (Lineages+)*) and/or those Lineages/Lineages+ that do not rank among the five most abundant in the interval of time and country selected by the user. Similarly, only the ten most numerous Mutations are explicitly shown, independently from the user selection. In this case the category *Others* is used to collapse all the Mutations that do not rank among the top ten most abundant. If you are dissatisfied with this behaviour and/or would like to modify the default values, please feel free to contact me at *e.ferrandi@ibiom.cnr.it* or here on GitHub.
