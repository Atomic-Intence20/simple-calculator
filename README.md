# simple calculator
 simple calculater_vlsi code

The simple_calculator module is a Verilog-based arithmetic unit that performs basic mathematical operations (addition, subtraction, multiplication, and division) on two 8-bit operands. The module operates sequentially, triggered by a clock signal, and provides a 16-bit result along with a done signal indicating the completion of the operation.

Features

Supports four arithmetic operations:

Addition (A + B)

Subtraction (A - B)

Multiplication (A * B)

Division (A / B, with division by zero handling)

Takes two 8-bit operands as input

Produces a 16-bit result

Synchronous operation using a clock signal

Reset functionality to initialize values

Module Interface

Inputs:

A [7:0]: First operand (8-bit)

B [7:0]: Second operand (8-bit)

op [1:0]: Operation selector:

00 -> Addition

01 -> Subtraction

10 -> Multiplication

11 -> Division

clk: Clock signal

reset: Active-high reset signal

Outputs:

result [15:0]: 16-bit output storing the operation result

done: Signal indicating the completion of an operation

Operation Details

The module executes the arithmetic operation on the rising edge of clk.

If reset is high, result is set to 0x0000 and done is reset to 0.

The selected operation is executed based on the op input.

If division by zero occurs, the module outputs 0xFFFF as an error indicator.

Once an operation is completed, done is set to 1.
