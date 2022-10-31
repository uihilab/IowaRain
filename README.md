# IowaRain

IowaRain is a dataset covering rain events ranging from 2016 through the end of 2019 for the state of Iowa. Each event contains a set of 2D Rain rate maps along with the size of the event, meaning the number of rain rate maps in the set, and the start date of the event.

## Rainfall Event Criteria 

The criteria for a set of snapshots are defined as follows;

- All snapshots in the set must be consecutive
- The set must consist of at least ten snapshots
- Each snapshot must have at least 0.5 mm/hr precipitation over %10 of the domain.

## Download the Dataset

The dataset can be downloaded from cloud as an archive file at https://mega.nz/file/pDMAAajR#GvUg7JV_HmByDLJYS1w6mEw9nh9o9f_YM_v9jl1R1Cw. The extracted directory has the following structure;

```
rainfall_events
├──── 2016
├──── 2017
├──── 2018
└──── 2019
```

 Each year directory contains events from the respective year.

**Opening Individual Event Files**

```python
>>> import gzip
>>> import pickle
>>> 
>>> with gzip.open('rainfall_events/2016/event_0.pgz', 'rb') as f:
...     event = pickle.load(f)
... 
>>> event[0]
datetime.datetime(2016, 4, 6, 2, 10)
>>> event[1]
75
>>> type(event[2])
<class 'list'>
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements & Citation

This project is developed by the University of Iowa Hydroinformatics Lab (UIHI Lab):

https://hydroinformatics.uiowa.edu/.

>Sit, M., Seo, B.C. and Demir, I., 2021. Iowarain: A statewide rain event dataset based on weather radars and quantitative precipitation estimation. arXiv preprint arXiv:2107.03432.
