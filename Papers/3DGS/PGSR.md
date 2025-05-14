# [SIGGRAPH'24] PGSR: Planar-based Gaussian Splatting for Efficient and High-Fidelity Surface Reconstruction


## Result of DTU ⬇

| Method               | 24   | 37   | 40   | 55   | 63   | 65   | 69   | 83   | 97   | 105  | 106  | 110  | 114  | 118  | 122  | Mean | Time(min)   |
|----------------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|-------------|
| Paper (3090)         | 0.36 | 0.57 | 0.38 | 0.33 | 0.78 | 0.58 | 0.50 | 1.08 | 0.63 | 0.59 | 0.46 | 0.54 | 0.30 | 0.38 | 0.34 | 0.52 | 30          |
| Reproduce (4090)     | 0.34 | 0.54 | 0.42 | 0.34 | 0.78 | 0.56 | 0.49 | 1.09 | 0.63 | 0.59 | 0.47 | 0.53 | 0.30 | 0.37 | 0.34 | 0.49 | 16.12       |


## Result of TNT ⬆

- f-socre
  
  _Reproduce_1 is get tnt dataset from [convert_tnt_1500.py](../../Preliminaries/preprocess/convert_tnt_1500.py) that came from neuralangelo_

  _Reproduce_2 is get tnt dataset from [convert_tnt.py](../../Preliminaries/preprocess/convert_tnt.py) that came from pgsr_

  
  

| Method              | Barn   | Caterpillar   | Courthouse| Ignatius   | Meetingroom   | Truck   | Mean   | Time(min)   | 
|---------------------|--------|---------------|-----------|------------|---------------|---------|--------|-------------|
| Paper (4090)        | 0.66   | 0.44          | 0.20      | 0.81       | 0.33          | 0.66    | 0.52   | 45          |
| Reproduce_1 (4090)  | 0.65   |   0.43        | 0.20      | 0.81       | 0.32          | 0.64    | 0.51   | 27.00       | 
