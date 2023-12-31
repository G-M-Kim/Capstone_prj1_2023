# Capstone_prj1_2023
Pipeline CPU with Systolic array based on RISC-V architecture.

# this project includes...
- 5-stage Pipeline structure
- Dynamic branch prediction using 2bit counter
- Systolic array for matrix operation acceleration
- test examples (bubble sort, successive matrix multiplication) in Inst_mem
- Simulation result pictures (systolic array, matrix mult, bubble sorting)

### The project is a copy of our work in the following organization ###
https://github.com/Convergent-Capstone-Design-team1

-----------------------------------------------------------------------------------------------------

We've used iverilog to compile- and simulated on gtkwave. 

use this code to compile CPU : 
iverilog -s tb_CPU -o test PC.v PC_mux.v BHT.v BTB.v Predictor.v Inst_mem.v Register_file.v Control.v ImmGen.v ALU_control.v ALU.v ALU_mux.v Forwarding_Unit.v Forwarding_mux.v Data_mem.v Hazard_detection.v IF_stage.v IF_ID.v ID_stage.v ID_EX.v EX_stage.v EX_MEM.v MEM_stage.v MEM_WB.v WB_stage.v Register.v TopCPU.v ID_EX_Flush.v EX_MEM_Flush.v Falling_edge_detector.v INITIAL_module.v tb_CPU.v

use this code to compile npu :
iverilog -s tb_systolic_array -o test mac.v systolic_array.v tb_systolic_array.v

use this code to compile combined module :
iverilog -s tb_combined -o test PC.v PC_mux.v BHT.v BTB.v Predictor.v Inst_mem.v Register_file.v Control.v ImmGen.v ALU_control.v ALU.v ALU_mux.v Forwarding_Unit.v Forwarding_mux.v Data_mem.v Hazard_detection.v IF_stage.v IF_ID.v ID_stage.v ID_EX.v EX_stage.v EX_MEM.v MEM_stage.v MEM_WB.v WB_stage.v Register.v TopCPU.v ID_EX_Flush.v EX_MEM_Flush.v Falling_edge_detector.v INITIAL_module.v MAC.v Systolic_array.v NPU.v combined.v tb_combined.v


after you compile, you can use these codes to simulate this modules :
vvp ./test
gtkwave test.vcd

or, you can just open the gtkw file we've made to check the operation.

### Project ended on June 2023. ###
