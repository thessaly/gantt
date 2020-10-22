# Gantt

A simple R snippet for getting a gantt chart with tasks and milestones in csv files, using the wonderful [Ganttrify](https://github.com/giocomai/ganttrify) package developed by [Giorgio Comai](https://github.com/giocomai).

## Output
![](plot.png)

## Data input

Input is divided in two csv files: `tasks.csv` and `spots.csv`

### Tasks
`tasks.csv` has four columns: 

```
wp,activity,start_date,end_date
1.Analysis,1.1 Finish coding,1,1
2. Missing data,2.1 Detect missing data,2,2
2. Missing data,2.2 Protocols for missing data collection,2,2
```

- wp is the main block that comprises different tasks, its length is calculated by adding the duration of inner tasks, should have a number
- activity should have a numbered 1.1, 1.2 etc scheme, you can number many activities with the same prefix if you want one activity to be performed in one line but with interruptions 
- start_date and end_date are integers representing months.

### Milestones

`spots.csv` has three columns: 

```
activity,spot_type,spot_date
3.5 Review State of the Art,D3,10
3.7 Write methods,D4,13
```

- activity has to be a copy of the text you have in an activity in `tasks.csv` where you want the milestone to be
- spot_type has the text that will go in the milestone label
- spot_date is an integer indicating the month where the label will go



