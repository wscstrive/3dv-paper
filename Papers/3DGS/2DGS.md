# [SIGGRAPH'24] 2D Gaussian Splatting for Geometrically Accurate Radiance Fields


## Result of DTU ⬇

| Method               | 24   | 37   | 40   | 55   | 63   | 65   | 69   | 83   | 97   | 105  | 106  | 110  | 114  | 118  | 122  | Mean | Time(min)   |
|----------------------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|------|-------------|
| Paper (3090)         | 0.48 | 0.91 | 0.39 | 0.39 | 1.01 | 0.83 | 0.81 | 1.36 | 1.27 | 0.76 | 0.70 | 1.40 | 0.40 | 0.76 | 0.52 | 0.80 | 10.9        |
| Reproduce (4090)     | 0.50 | 0.79 | 0.36 | 0.43 | 1.39 | 0.84 | 0.80 | 1.27 | 1.25 | 0.64 | 0.66 | 1.08 | 0.42 | 0.61 | 0.55 | 0.86 | 6.6833      |

## Result of TNT ⬆

- f-socre
  
  _Reproduce_1 is get tnt dataset from [convert_tnt_1500.py](../../Preliminaries/preprocess/convert_tnt_1500.py) that came from neuralangelo_

  _Reproduce_2 is get tnt dataset from [convert_tnt.py](../../Preliminaries/preprocess/convert_tnt.py) that came from pgsr_

  
  

| Method              | Barn   | Caterpillar   | Courthouse| Ignatius   | Meetingroom   | Truck   | Mean   | Time(min)   | 
|---------------------|--------|---------------|-----------|------------|---------------|---------|--------|-------------|
| Paper (3090)        | 0.41   | 0.23          | 0.16      | 0.51       | 0.17          | 0.45    | 0.32   | 15.5        |
| Reproduce_1 (4090)  | 0.4130 | 0.2390        | 0.1287    | 0.4958     | 0.1684        | 0.4195  | 0.3107 | 10.08       | 
| Reproduce_1 (4090)  | 0.4070 | 0.2431        | 0.1278    | 0.4925     | 0.1830        | 0.4293  | 0.3138 |  10.19      | 


| Reproduce_1        | Barn   | Caterpillar   | Courthouse| Ignatius   | Meetingroom   | Truck   | Mean   |
|--------------------|--------|---------------|-----------|------------|---------------|---------|--------|
| distance tau       | 0.010  | 0.005         | 0.025     | 0.003      | 0.010         | 0.005   | 0.0097 |
| precision          | 0.3554 | 0.1660        | 0.0990    | 0.4188     | 0.1922        | 0.3453  | 0.2628 |
| recall             | 0.4930 | 0.4267        | 0.1839    | 0.6075     | 0.1499        | 0.4195  | 0.3801 |

| Reproduce_1        | Barn   | Caterpillar   | Courthouse| Ignatius   | Meetingroom   | Truck   | Mean   |
|--------------------|--------|---------------|-----------|------------|---------------|---------|--------|
| distance tau       | 0.010  | 0.005         | 0.025     | 0.003      | 0.010         | 0.005   | 0.0097 |
| precision          | 0.3445 | 0.1686        | 0.0936    | 0.4158     | 0.1907        | 0.3578  | 0.2618 |
| recall             | 0.4970 | 0.4357        | 0.2014    | 0.6040     | 0.1760        | 0.5366  | 0.4085 |

## Result of MipNeRF360

|          -        |   -   | Outdoor Scene |     -     |      -     | Indoor Scene   |         | 
|-------------------|-------|---------------|-----------|------------|---------------|---------|
| Method            | PSNR⬆ | SSIM ⬆        | LIPPS ⬇   | PSNR ⬆     | SSIM ⬆        | LIPPS ⬇ | 
|  Paper (3090)     | 24.34  | 0.717          | 0.246      | 30.40       | 0.916          | 0.195    | 
| Reproduce (4090)  | 24.60 | 0.7046         | 0.2844     | 30.04      | 0.9115         | 0.2119   | 

