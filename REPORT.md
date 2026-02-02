Section 1, Instructions:

0x00000024 is the R-type instruction for AND

0x00000025 is the R-type instruction for OR

0x00000020 is the R-type instruction for ADD

0x00000022 is the R-type instruction for SUB

0x0000002A is the R-type instruction for SLT

0x00000027 is the R-type instruction for NOR

0x20000004 is the ADDI instruction (add immediate)

0x8C000020 is the LW instruction (load word)

0xAC000064 is the SW instruction (store word)

0x10000025 is the BEQ instruction (branch if equal)



Section 2, differences in add and addi:

The add and addi instructions perform similar arithmetic operations, but they differ in how their operands and destination registers are selected in the datapath, which leads to differences in certain control signals.

reg_dst:
-For add, reg_dst is set to 1 because the destination register is the rd field of the instruction. 
-For addi, reg_dst is set to 0 because the destination register is the rt field.

alu_src:
-For add, alu_src is set to 0 so that the ALU’s second operand comes from a register.
-For addi, alu_src is set to 1 so that the ALU’s second operand comes from the immediate value instead of a register.

alu_op:
-For add, alu_op is set to be an R-type instruction, so that the ALU control can use the function field.
-For addi, alu_op is set to the add operation directly, since the instruction  does not use the function field.