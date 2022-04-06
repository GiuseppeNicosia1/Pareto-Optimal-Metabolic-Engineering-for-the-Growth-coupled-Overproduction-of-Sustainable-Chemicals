The software has been tested on Matlab r2022a.


--------------------
1) Initial settings
--------------------

Download COBRA toolbox for MATLAB from http://opencobra.github.io/ and set the local COBRA folder with the instruction
>> addpath(genpath('path_to_COBRA_toolbox'));



--------------------------------
2) Multi-objective optimization 
--------------------------------

Load the model (e.g. the one with succinate-biomass set as objectives)

fbamodel.f selects the first objective (e.g., biomass)
fbamodel.g selects the second objective (e.g., succinate)

To find the indices of the reactions, and then change lower and upper bounds (fbamodel.lb and fbamodel.ub), please type
>> n=find(ismember(fbamodel.rxns, 'EX_succ(e)')==1)
>> n=find(ismember(fbamodel.rxns, 'EX_ac(e)')==1)

>> n=find(ismember(fbamodel.rxns, 'EX_o2(e)')==1)
(use this to change between aerobic and anaerobic conditions; aerobic conditions are considered with a flux of -10 mmol/h/gDW, anaerobic conditions are with 0 uptake rate)








