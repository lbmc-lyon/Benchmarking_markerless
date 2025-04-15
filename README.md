# Benchmarking platform for markerless motion capture analysis

We propose a benchmarking platform for markerless motion capture analysis, comparing markerless approaches against traditional marker-based motion analysis.

This platform consists of two main components:
1) A data repository containing experimental data (videos + marker trajectories) (https://doi.org/10.57745/LQI2MJ).
2) This GitHub repository, which includes:
    - joint motion estimations obtained using several markerless methods (with a description of each methodology);
    - joint motion estimation obtained using marker-based data;
    - sample code to compare results [`compare_results.ipynb`](./compare_results.ipynb).

You can download the data, benchmark your own method, and compare it to the existing results.
If desired, you may also contribute to the benchmarking dataset by integrating your method with corresponding results.

## Marker-based workflow

For each participant, the biomechanical model was generated based on the regression method detailed in [Dumas and Wojtusch (2018)](#2).
Based on this model, joint coordinates were calculated using a Multibody Kinematics Optimization (MKO). Each joint was defined as a free joint (6 dof). The MKO was performed with [biorbd](https://github.com/pyomeca/biorbd) ([Michaud and Begon, 2021](#1)).

## Analysis variables

For each task and each participant, the 10 joint motions of interest are:
- right hip flexion/extension (`RHip_FE`) ;
- right hip adduction/abduction (`RHip_AA`) ;
- right knee flexion/extension (`RKnee_FE`) ;
- right ankle flexion/extension (`RAnkle_FE`) ;
- L5/S1 joint flexion/extension (`L5S1_FE`) ;
- right shoulder adduction/abduction (`RShoulder_AA`) ;
- right shoulder internal/external rotation (`RShoulder_RIE`) ;
- right elbow flexion/extension (`RElbow_FE`) ;
- right elbow pronation/supination (`RElbow_PS`) ;
- right wrist flexion/extension (`RWrist_FE`).

## Data organisation

The output data from each markerless method is stored in a dedicated folder, which contains:
- **one csv file per participant per task**: named as `task_participant.csv`;
- **a summary csv file**: `Summary.csv`, which provides an overview of the methodologies used for the analysis.

Templates for these files are available in the `Template` folder.

## Comparison

The jupyter notebook `compare_results.ipynb` allows for the comparison of different results.

## How to contribute?

Just do a Pull Request with your data!  
Your data must include the Summary.xlsx file with a set of task_participant.csv files (see [Data organisation](#data-organisation))

## References
<a id="2">[Dumas and Wojtusch, 2018]</a> 
Dumas, R., & Wojtusch, J. (2018).
Estimation of the Body Segment Inertial Parameters for the Rigid Body Biomechanical Models Used in Motion Analysis.
*Handbook of Human Motion*, pp-47.

<a id="1">[Michaud and Begon, 2021]</a> 
Michaud, B., & Begon, M. (2021).
biorbd: A c++, python and matlab library to analyze and simulate the human body biomechanics.
*Journal of open source software*, 6(57), 2562.
(https://doi.org/10.21105/joss.02562)




