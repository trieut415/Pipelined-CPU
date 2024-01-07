For this project, we were given a partially completed 32-bit 4 stage pipelined datapath, and we had to add functionality to support data hazards and forwarding, and including support for R-Type and I-Type instructions in MIPS with these requirements: The most significant bit (31) is unused.
• The next most significant bit of the opcode (30) determines whether the instruction is Logical/Arithmetic
(1) or other (0). This will always be set for this lab.
• The third bit of the opcode (29) determines whether the instruction uses an immediate operand (1) or not
(0). That is, if this bit is set, the instruction follows the I-type template.
• The least significant 3 bits of the opcode field (28-26) are fed into the ALU’s ALUOp input.
• The ALU has the following functions:

For the register file, we essentially tested a wide variety of values given the testbench, and
evaluated the waveforms to see if the data was correctly parsed and passed to each ReadSelect, and ReadData, given the correct WriteEnable signal. This was also pretty easy to test with our top level, as we began to pass instructions that carried throughout the circuit.


With the ALU testbench, we essentially just passed a series of hard-coded values, simulating
immediates, and also tested in unison with the register to ensure that we had a output that made
sense given the appropriate commands, such as reading in data from the Data source.
3. Description of how you tested the datapath and timing diagram
This is our timing diagram of the entire datapath, as you can see the first 5 instructions on the last row are able to use the MUX to direct data into the ALU if the I-type instruction was specified. In the last 5 instructions, the R-Type instructions are called, requiring that the data be updated and fetched on the positive edge of the clock.
