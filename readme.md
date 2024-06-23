# Supplementary information for 
### *Designing Metal-Organic Frameworks for Carbon Capture Using Multi-Scale Approaches with Machine Learning and Multi-Objective Optimization*

*Zijun Deng, Lev Sarkisov*


This repository contains the scripts to the article *Designing Metal-Organic Frameworks for Carbon Capture Using Multi-Scale Approaches with Machine Learning and Multi-Objective Optimization* by Zijun Deng and Lev Sarkisov. 


Note:
-----
The scripts are provided as-is, and are not guaranteed to work without the required dependencies or with different structure from that used in our work. If you have any questions, please contact the corresponding author of the article.


##	How to generate optimal MOFs using ML-NSGA models
Requirement: Jupyter Notebook, Python with packages - NumPy, Pandas, Pickle, Pymoo, PORMAKE (https://github.com/Sangwon91/PORMAKE)

1.	Go to the directory "ML_NSGA" and run the script “carbon_problem.ipynb”, “carbon_problem_dni-d.ipynb”, “carbon_problem_twf.ipynb”, and “carbon_problem_uru.ipynb” in Jupyter Notebook
2.	Obtain the MOF list in "NSGAML/nsga_result"
3.	Generate MOFs based on the MOF list, using PORMAKE.


##	How to compute adsorption uptakes by GCMC simulations
Requirement: RASPA

1.	Assign partial charge to structures using PACMOF packge (https://github.com/arung-northwestern/pacmof)
2.	Compute adsorption loading using RASPA. Force field and input files are provided in the folder "GCMC".  See the link for more details: https://github.com/iRASPA/RASPA2/blob/master/Docs/raspa.pdf


##	How to train ML models
Requirement: Jupyter Notebook, Python with packages - MOFNet (https://github.com/Sangwon91/MOF-NET)

1.	Go to "ML_training/CO2" and "ML_training/N2". Put add adsorption data into the file "cycle_tot.txt".
2.	Train ML models by running the script “train_mofnet.ipynb” in Jupyter Notebook.
3.	Copy the model files in "ML_training/CO2/cycle_tot" and "ML_training/N2/cycle_tot" to "ML_NSGA/cycle_tot" and "ML_NSGA/cycle_tot_n2", respectively.


##	How to compute productivity-energy pareto fronts by process modeling and optimization
Requirement: MATLAB
1.	Obtain adsorption isotherms at various temperature and fit these data points in a DSL model.
2.	Override the DSL parameters the row 2 of the table “PSA/sorted_material_dataframes/DRE_DDEC_material_data.csv“ with your DSL model. 
3.	Run the script “ProcessOptValidation.m” using MATLAB
