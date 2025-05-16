# [SIGGRAPH'24] 2D Gaussian Splatting for Geometrically Accurate Radiance Fields


## Result of DTU ⬇

| Method               | 24   | 37   | 40   | 55   | 63   | 65   | 69   | 83   | 97   | 105  | 106  | 110  | 114  | 118  | 122  | Mean | Time(min)   |
|----------------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|-------------|
| Paper (3090)         | 0.48 | 0.91 | 0.39 | 0.39 | 1.01 | 0.83 | 0.81 | 1.36 | 1.27 | 0.76 | 0.70 | 1.40 | 0.40 | 0.76 | 0.52 | 0.80 | 10.9        |
| Reproduce (4090)     | 0.49 | 0.81 | 0.34 | 0.44 | 1.01 | 0.87 | 0.82 | 1.31 | 1.22 | 0.64 | 0.68 | 1.29 | 0.42 | 0.67 | 0.48 | 0.766| 6.69        |

## Result of TNT ⬆

- f-socre
  
  _Reproduce_1 is get tnt dataset from [convert_tnt_1500.py](../../Preliminaries/preprocess/convert_tnt_1500.py) that came from neuralangelo_

  _Reproduce_2 is get tnt dataset from [convert_tnt.py](../../Preliminaries/preprocess/convert_tnt.py) that came from pgsr_

  
  

| Method              | Barn   | Caterpillar   | Courthouse| Ignatius   | Meetingroom   | Truck   | Mean   | Time(min)   | 
|---------------------|--------|---------------|-----------|------------|---------------|---------|--------|-------------|
| Paper (3090)        | 0.41   | 0.23          | 0.16      | 0.51       | 0.17          | 0.45    | 0.32   | 15.5        |
| Reproduce_1 (4090)  | 0.4130 | 0.2390        | 0.1287    | 0.4958     | 0.1684        | 0.4195  | 0.3107 | 10.08       | 
| Reproduce_1 (4090)  | 0.4070 | 0.2431        | 0.1278    | 0.4925     | 0.1830        | 0.4293  | 0.3138 |  10.19      | 


## Result of MipNeRF360

|          -        |   -   | Outdoor Scene |     -     |      -     | Indoor Scene   |         | 
|-------------------|-------|---------------|-----------|------------|---------------|---------|
| Method            | PSNR⬆ | SSIM ⬆        | LIPPS ⬇   | PSNR ⬆     | SSIM ⬆        | LIPPS ⬇ | 
|  Paper (3090)     | 24.34  | 0.717          | 0.246      | 30.40       | 0.916          | 0.195    | 
| Reproduce (4090)  | 24.60 | 0.7046         | 0.2844     | 30.04      | 0.9115         | 0.2119   | 

