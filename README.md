# VSDsquadron  Internship

<details>
<summary><b> Task 1: </b> Install RISC-V toolchain using VDI and compile a simple C code using RISC-V kit</summary>
 <br>

 **1. Installing virtual box :**

 ![Installing virtual box](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/84ca4811-56a8-4164-9bd8-4f809d448b7e)

**2.Installing leafpad :**

![Installing leaf pad](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/93ab7ba8-10fa-4c10-b52f-a66cfb0f9a91)

To install the leafpad, we should use the command 
``` sudo apt install leafpad ```
as above.

**3.Compiling and run sample C code :**

Step-1: We have to create a file for the sample code using the command,
```
    cd
    leafpad sum1ton.c &
```
Hence, the leafpad will get open.
   
Step-2 : Next we need to type the C code in the leafpad as below:

![sample C code](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/cb649f45-782b-4213-b95a-a99bc4873d44)

then we should save the code.

Step-3: To run this code in terminal, we need to use the command 
```
    gcc sum1ton.c
    ls -ltr
```

To get the output, we should use the command ``` ./a.out ```

By using the above commands, we will get the output as

![Sample C output](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/25fca97a-b86a-401f-abd9-7d22443b9f44)

**4.compiling and run sample code using RISC-V simulator :**

Step-1: To get the code into the simulator, use the command
```
   cat sum1ton.c
```

Step-2: To run the code using the simulator, use the command
```
   riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
   ls -ltr sum1ton.o
```

![calculations of instructions using fast instructions](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/6f5dd289-557a-4190-ad00-b2e4008b4e17)

Step-3: **To get the Assembly code output :**

Use the command,
 ```
     riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
 ```
Then open another tab and use the following command:
```
    riscv64-unknown-elf-objdump -d sum1ton.o
```
After using the command you will get the complex assembly output.

To get the exact assembly output of your code, use the command
    
```
    riscv64-unknown-elf-objdump -d sum1ton.o | less
```

And finally search the main using ```/main```

Hence, you will get the final output of this task as 

![calculations of instructions](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/059d35ea-d38b-46cb-a276-20b81dde9fb9)

</details>


<details>
 <summary> <b> Task 2 :</b> To write a C program for my project and compile with RISC-V GCC</summary>
 <br>

 **Project Title : Change dispense wizard: Engineering a vending machine with advanced change system**

 **What is Vending Machine :**

 An automated machine which is intended to provide the users with a diverse range of products: snacks, beverages, pizzas, cupcakes, newspapers, tickets, etc. A vending machine dispenses a product to the users based on the amount of money inserted and selection of the product. Vending machine is a 24x7 standalone unit which requires a standard power supply connection to function. It consist of simple electro-mechanical systems which helps to automate the entire vending process. In a nutshell, its basic function is to flawlessly issue users with a diverse range of products anytime.

 **What is Channge dispense wizard in vending machine :**

 The "Change Dispense Wizard" is a specialized framework designed to enhance the process of dispensing change in vending machines. This advanced system incorporates mechanical, electronic, and software components to ensure accurate, efficient, and reliable coin dispensing.

 **Benefits :**

 **1.Enhanced Customer Satisfaction :**
Quick and accurate change dispensing improves the overall user experience.

**2.Operational Efficiency :**
Reduces the likelihood of errors and machine downtime.

**3.Increased Security :**
Protects against fraud and tampering.

**4.Scalability :**
Can be adapted to different types of vending machines and environments.

![vm](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/b0f6f497-276a-4a0a-9df7-5de1bdb13796)

**Program for the Project :**

```
#include <stdio.h>

// Function to calculate and dispense change
void dispenseChange(int amount) {
    int quarters, dimes, nickels, pennies;

    quarters = amount / 25;
    amount = amount % 25;

    dimes = amount / 10;
    amount = amount % 10;

    nickels = amount / 5;
    amount = amount % 5;

    pennies = amount;

    printf("Change dispensed:\n");
    printf("Quarters: %d\n", quarters);
    printf("Dimes: %d\n", dimes);
    printf("Nickels: %d\n", nickels);
    printf("Pennies: %d\n", pennies);
}

int main() {
    int cost, paid, change;

    // Get the cost of the item
    printf("Enter the cost of the item (in cents): ");
    scanf("%d", &cost);

    // Get the amount paid by the user
    printf("Enter the amount paid by the user (in cents): ");
    scanf("%d", &paid);

    // Calculate the change to be returned
    change = paid - cost;

    if (change < 0) {
        printf("Insufficient amount paid.\n");
    } else if (change == 0) {
        printf("Exact amount paid. No change needed.\n");
    } else {
        // Dispense the change
        dispenseChange(change);
    }

    return 0;
}
```

**1.Declaring VendingMachine in Terminal :**

![1 Declaring Vending Machine](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/326b5cab-738b-428d-abe3-e7bfc9925b75)

**2.Typing the code in leafpad :**

![2 C program for the Vending Machine](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/d88f6d2c-9a71-4a0c-9b14-7379b9dcf964)

**3.Executing the code and getting th output :**

![3 Input Output of  VendingMachine](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/d65706c0-b1e6-490b-af5f-d4ee232cd4fa)

**4.compiling and run the code in RISC-V GCC :**

![4 Instructions for assembly code of VendingMachine](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/8a890a71-771e-44dd-8d68-49acc8f29740)

**5.Assembly code output of VendingMachine :**

![5 Assembly code output of VendingMachine](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/3b77559c-7c69-45f4-bbb5-f1a9eb6a9ef5)

This is the final output of the project.
</details>


<details>
 <summary><b> Task 3: </b> Perform the Spike simulation using -o1 and -ofast commands and upload the result. </summary>
 <br>

 In this task we have to perform the spike simulation using two different commands :
 1. -o1 command
 2. -ofast command

 **I.Spike simulation using -o1 command:**

 1.First run your program using riscv simulator and get the output using the command,
 ```
 riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o vendingmachine.o vendingmachine.c
 gcc vendingmachine.c
 ./a.out
 ```

 2.Now run the same program using spike simulator using the command,
 ```
 riscv64-unknown-elf-gcc -o1 -mabi-lp64 -march=rv64i -o vendingmachine.o vendingmachine.c
 spike pk vendingmachine.o
 ```

 3.check the both outputs. If the both outputs are same then the compilation is successful.

 ![1 Spike simulation using -o1 command](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/4b796a3f-62ab-4cfc-9485-6834a2070c3e)

 4.Now go for debugging the assembly code using spike debugging command.
 
   To get the assembly code, use the command
   ```
   riscv64-unknown-elf-objdump -d vendingmachine.o | less
   ```

 ![Screenshot (31)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/36389a45-f5e7-4717-a019-ec18e3a0c926)

 To debug the code, use the spike command
 ```
 spike -d pk vendingmachine.o
 ```

 And then use the starting address of the assembly code ```until pc 0 100b0``` and compare the both address lines to check the result.

 ![Screenshot (32)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/9c88ebf5-027f-4ff3-b14e-2a6bead12f03)

 ![Screenshot (33)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/db81e921-7624-4517-8b5b-d3c60b853b9a)

 **II.Spike simulation using -ofast command:**

 This process is same like the above one. But instead of -o1 command, we use the -ofast command.
 
 1.Use the command to get the output using riscv simulator,
 ```
 riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o vendingmachine.o vendingmachine.c
 gcc vendingmachine.c
 ./a.out
 ```

 2.To get the spike simulation output, use the command
 ```
 riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o vendingmachine.o vendingmachine.c
 spike pk vendingmachine.o
 ```

 3.Check the both outputs. If both outputs are same then the compilation is successful.

 ![Screenshot (30)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/c2a3beaa-4b7a-4b70-a38c-62a63d89c542)

 4.Now we need to debug the assembly code.
 
 To get the assembly code, use the command 
 ```
 riscv64-unknown-elf-objdump -d vendingmachine.o | less
 ```

 ![Screenshot (31)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/54a8e1d2-11d2-4633-a46a-0e2666bd082b)

 To debug the assembly code, use the spike command
 ```
 spike -d pk vendingmachine.o
 ```

 Use the starting address ```until pc 0 100b0``` and continue debugging and check the results using both address line outputs.

 ![Screenshot (32)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/c57f17ee-f2bb-46c1-a04f-01cb02643d6a)

 ![Screenshot (33)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/af0d6e41-e403-4a24-bf3c-3e24b5f3efff)

 So, that's the end of the task 3.

</details>


<details>
 <summary><b> Task 4: </b> To identify various instruction type and exact 32-bit instruction code in the instruction type format for given RISC-V instructions. </summary>
 <br>

 *Chat gpt is used as an external source for gathering the information.*

 **What is RISC-V ?**

 RISC-V is an open, free, and extensible instruction set architecture (ISA) based on reduced instruction set computing (RISC) principles. It is designed to be simple, modular, and scalable, suitable for a wide range of applications from small embedded systems to high-performance processors. RISC-V is maintained by the RISC-V Foundation, promoting innovation and collaboration without licensing fees. Its open nature allows for customization and widespread adoption in both academic research and commercial development.

The RISC-V architecture defines several instruction formats for 32-bit instructions.

![MUKIE](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/60ffaf38-af65-4af4-9369-3b1a05978e41)

 **Types of Instruction set formats:**

 **1.R-Type (Register-Register Operations):**

 - Used for: Arithmetic and logical operations.
 - Format:
   ```
    31       25 24    20 19    15 14    12 11       7 6       0
    +--------+--------+--------+--------+--------+--------+
    | funct7 |  rs2   |  rs1   | funct3 |   rd   | opcode |
    +--------+--------+--------+--------+--------+--------+
   ```
 - funct7: 7-bit function code
 - rs2: 5-bit source register 2
 - rs1: 5-bit source register 1
 - funct3: 3-bit function code
 - rd: 5-bit destination register
 - opcode: 7-bit opcode

 **2.I-Type (Immediate Operations):**

 - Used for: Immediate arithmetic, loads, and system calls.
 - Format:
 ```
  31       20 19    15 14    12 11       7 6       0
  +--------+--------+--------+--------+--------+
  | imm[11:0] |  rs1   | funct3 |   rd   | opcode |
  +--------+--------+--------+--------+--------+
 ```
 - imm: 12-bit immediate value
 - rs1: 5-bit source register 1
 - funct3: 3-bit function code
 - rd: 5-bit destination register
 - opcode: 7-bit opcode

 **3.S-Type (Store Instructions):**

 - Used for: Store operations
 - Format:
 ```
 31       25 24    20 19    15 14    12 11       7 6       0
 +--------+--------+--------+--------+--------+--------+
 | imm[11:5] |  rs2   |  rs1   | funct3 | imm[4:0] | opcode |
 +--------+--------+--------+--------+--------+--------+
 ```
 - imm: 12-bit immediate value (split between imm[11:5] and imm[4:0])
 - rs2: 5-bit source register 2 (value to be stored)
 - rs1: 5-bit source register 1 (base address)
 - funct3: 3-bit function code
 - opcode: 7-bit opcode

 **4.B-Type (Branch Instructions):**

 - Used for: Conditional branches
 - Format:
 ```
 31       25 24    20 19    15 14    12 11       7 6       0
 +--------+--------+--------+--------+--------+--------+
 | imm[12|10:5] |  rs2   |  rs1   | funct3 | imm[4:1|11] | opcode |
 +--------+--------+--------+--------+--------+--------+
 ```
 - imm: 12-bit immediate value (split between imm[12|10:5] and imm[4:1|11])
 - rs2: 5-bit source register 2
 - rs1: 5-bit source register 1
 - funct3: 3-bit function code
 - opcode: 7-bit opcode

 **5.U-Type (Upper Immediate Instructions):**

 - Used for: Loading upper immediate, for large constants
 - Format:
 ```
  31       12 11       7 6       0
  +--------+--------+--------+
  |       imm[31:12]       |   rd   | opcode |
  +--------+--------+--------+
 ```
 - imm: 20-bit immediate value
 - rd: 5-bit destination register
 - opcode: 7-bit opcode

 **6.J-Type (Jump Instructions):**

 - Used for: Unconditional jumps
 - Format:
 ```
  31       12 11       7 6       0
  +--------+--------+--------+
  | imm[20|10:1|11|19:12] |   rd   | opcode |
  +--------+--------+--------+
 ```
 - imm: 20-bit immediate value (split between imm[20|10:1|11|19:12])
 - rd: 5-bit destination register (link address)
 - opcode: 7-bit opcode

 These formats provide a consistent and efficient way to encode the diverse set of instructions in the RISC-V ISA. Each format is tailored to the specific needs 
 of different types of operations, ensuring both simplicity and flexibility in instruction encoding.

 **Now let's compute the instruction code for the given instructions in the below figure:**

 ![Screenshot 2024-07-08 125025](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/3e457e0d-9569-45d7-98bb-c9240fac2e66)


 **1.ADD r1,r2,r3**
 
  Type: R
  
  Opcode: 0110011
  
  rd : 00001
  
  funct3: 000
  
  rs1 : 00010
  
  rs2 : 00011
  
  funct7: 0000000
  
 *32-bit instruction code:*
  ```
   0000000 00011 00010 000 00001 0110011
  ```

 **2.SUB r3, r1, r2**

   Type: R
   
   Opcode: 0110011
   
   rd: 00011
   
   funct3: 000
   
   rs1 : 00001
   
   rs2 : 00010
   
   funct7: 0100000
   
   *32-bit instruction code:*
   ```
    0100000 00010 00001 000 00011 0110011
   ```

 **3.AND r2,r1,r3**

   Type: R
   
   Opcode: 0110011
   
   rd : 00010
   
   funct3: 111
   
   rs1 : 00001
   
   rs2 : 00011
   
   funct7: 0000000
   
   *32-bit instruction code:*
   ```
    0000000 00011 00001 111 00010 0110011
   ```

 **4.OR r8, r2, r5**

 Type: R
 
 Opcode: 0110011
 
rd : 01000

funct3: 110

rs1 : 00010

rs2 : 00101

funct7: 0000000

*32-bit instruction code:*
```
0000000 00101 00010 110 01000 0110011
```

 **5.XOR r8,r1,r4**

 Type: R
 
 Opcode: 0110011
 
rd : 01000

funct3: 100

rs1 : 00001

rs2 : 00100

funct7: 0000000

*32-bit instruction code:*
```
0000000 00100 00001 100 01000 0110011
```

 **6.SLT r10,r2,r4**

 Type: R

 Opcode: 0110011
 
rd : 01010

funct3: 010

rs1 : 00010

rs2 : 00100

funct7: 0000000

*32-bit instruction code:*
```
0000000 00100 00010 010 01010 0110011
```

**7.ADDI r12,r3,5**

Type: I

Opcode: 0010011

rd : 01100

funct3: 000

rs1 : 00011

imm: 000000000101

*32-bit instruction code:*
```
000000000101 00011 000 01100 0010011
```

 **8.SW r3,r1,r4**

 Type: S
 
 Opcode: 0100011
 
imm[4:0]: 00100

rs1 : 00001

rs2 : 00011

funct3: 010

imm[11:5]: 0000000

*32-bit instruction code:*
```
0000000 00011 00001 010 00100 0100011
```

 **9.SRL r16,r11,r2**

 Type: R
 
 Opcode: 0110011
 
rd : 10000

funct3: 101

rs1 : 01011

rs2 : 00010

funct7: 0000000

*32-bit instruction code:*
```
0000000 00010 01011 101 10000 0110011
```

 **10.BNE r0, r1, 20**

  Type: B
  
  Opcode: 1100011
  
imm[12|10:5]: 0000001

rs2: 00001

rs1: 00000

funct3: 001

imm[4:1|11]: 01000

*32-bit instruction code:*
```
0000000 00001 00000 001 00101 0000001
```

 **11.BEQ r0, r0, 15**

  Type: B
  
  Opcode: 1100011
  
funct3: 000

rs1: 00000

rs2: 00000

imm[11:0]: 15

*32-bit instruction code:*
```
0000000 00000 00000 000 01111 0000000
```

 **12.LW r13,r11,2**

 Type: I
 
 Opcode: 0000011
 
rd: 01101

funct3: 010

rs1: 01011

Immediate: 00010

*32-bit instruction code:*
```
000000000010 01011 010 01101 0000011
```

 **13.SLL r15,r11,r2**

 Type: R
 
 Opcode: 0110011
 
rd : 01111

funct3: 001

rs1 : 01011

rs2 : 00010

funct7: 0000000

*32-bit instruction code:*
```
0000000 00010 01011 001 01111 0110011
```

So, that's the end of this task.

</details>


<details>
 <summary><b> Task 5: </b> Using the  RISC-V Core verilog netlist and testbench for functional simulation experiment and uploading the waveform outputs.</summary>
 <br>

 **Follow the steps to obtain the waveforms of the instructions:**

 1. To run the verilog code, first we need a tool called *iverilog* and to install it, use the following commands
    ```
    sudo apt-get update
    sudo apt-get install iverilog
    ```
 2. Also, to get the waveforms we need another tool called gtkwave and to get that, use the command
    ```
    sudo apt-get install gtkwave
    ```
![Screenshot (36)](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/d9729f52-4e8b-4395-a878-7dbce07801b1)

 3. Create a directory using the command
    ```
    mkdir vasanth
    ```
 4. To create the files, use the following commands
    ```
    touch vasanth_rv32i.v
    touch vasanth_rv32i_tb.v
    ```
 5. Since we do not have the verilog code, we will take the references of verilog code and the waveform from
    https://github.com/vinayrayapati/rv32i/
 6. We will copy the code from ```iiitb_rv32i.v``` and ```iiitb_rv32i_tb.v``` and pastes the code in ```vasanth_rv32i.v``` and ```vasanth_rv32i_tb.v``` in leafpad and saves the file.
 7. To run and simulate the code, use the command
    ```
    iverilog -o vasanth_rv32i vasanth_rv32i.v vasanth_rv32i_tb.v
    ```
    And to get the output, use the command
    ``` 
    ./vasanth_rv32i
    ```
 8. To get the waveforms, use the command
    ```
    gtkwave iiitb_rv32i.vcd
    ```

 **Instructions and their waveforms:**

 *ADD r1,r2,r3*
 
 ![346928410-df93c271-0c7a-40eb-b56d-bb51291bc876](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/b856f2eb-ae5a-494c-8a54-41e3eb052c1d)

 *SUB r3,r1,r2*

 ![346928852-941520a3-bfc6-493c-a1a6-2722ca080308](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/173d9200-7bc4-45e6-bdf6-afd476dc5b59)

 *AND r2,r1,r3*

 ![346929050-98331053-fdcf-4b1c-a297-1dc1eeec9fbb](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/5ad81c65-8569-4498-bec4-8b3c4825c094)

 *OR r8,r2,r5*

 ![346929234-2d274efb-34a8-446a-874f-917d873712f0](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/210bdd8e-4a89-48c8-8682-e6935290b9c0)

 *XOR r8,r1,r4*

 ![346929985-f17cb96e-1fa2-4521-8c4c-6f79c29e3cf0](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/8cc7ac99-34c7-4d01-957a-38ca1bd4f24c)

 *SLT r10,r2,r4*

 ![346930138-421a1c05-8ccf-492c-92b7-d6d8685eb822](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/feb1459a-b11f-4290-b917-94988645a708)

 *ADDI r122,r3,r5*

 ![346930348-f731eed6-7c04-4a3d-a1c9-6ffa6dc47dfc](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/4bb365c5-2ff5-4100-9070-a82d575bd5cf)

 *SW r3,r1,r4*

 ![346930541-468b98fc-7cec-4787-9de5-cb4f74eb8300](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/79e2932e-4982-4a41-88f4-6816593a3f9d)

 *SRL r16,r11,r2*

 ![346930739-5d3ff2ea-491e-46d3-b3a3-7c4046339734](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/9f95768e-1480-460a-aa3b-387dce2a787c)

 *BNE r0,r1,20*

 ![346930933-d5572b5f-b740-47c2-8128-b64253a58fb1](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/ae679a3a-3d11-4815-82d1-73ac17dddbc0)

 *BEQ r0,r0,15*

 ![346931076-97870d87-2618-4069-82ef-f079c2f1ed27](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/f53b5196-64f2-46ec-a393-7d9aeb083aaa)

 *SLL r15,r11,r2*

 ![346931199-75f34f93-c023-4ee4-8a4c-a8e8b470c697](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/362d5997-7e7f-45d5-8e87-75affd3012bc)

 And that's the end of this task.
</details>


<details>
 <summary><b> Task 6: </b> Overview of the Project. </summary>
 <br>

 **Overview:**

 The project involves using a VSDsquadron mini board with RISC-V GCC to control a vending machine's change dispense system. It utilizes 4 LEDs as status indicators and 2 buttons for user input. The LEDs indicate different operational states, controlled by button presses. The software manages GPIO operations to toggle LEDs based on button states, simulating a vending machine's interaction for educational or prototyping purposes.

 **Components required for VendingMachine:**

 1. VSDsquadron Mini Board (RISC-V based microcontroller)
 2. LEDs (to indicate different statuses) - 4 LEDs
 3. Resistors (220Ω for LEDs) - 4 resistors
 4. Buttons (for user input) - 2 buttons
 5. Breadboard
 6. Connecting Wires
 7. Power Supply (5V adapter)

 **Circuit connection:**

 **1. LED Connections:**

 Place LED1 on the breadboard.
 - Connect the anode(long leg) to GPIO5 through a 220Ω resistor.
 - Connect the cathode(short leg) to the negative power rail.
   
 Repeat the same for LED2, LED3, and LED4, connecting their anodes to GPIO6, GPIO7, and GPIO8 respectively.

 **2. Button Connections:**

 Place Button1 on the breadboard.
 - Connect one side to GPIO9.
 - Connect the other side to the negative power rail.
 
 Repeat the same for Button2, connecting it to GPIO10.

 **3. Power Supply Connection:**

 Connect the 5V adapter to the breadboard power rails.
 - Connect VIN from the VSDsquadron mini to the positive power rail.
 - Connect GND from the VSDsquadron mini to the negative power rail.

 **Pinout diagram:**

 | VSDsquadron mini-board | Component |
 | -----------------------| ----------|
 | GPIO5 | LED1 (Anode) through 220Ω Resistor |
 | GPIO6 | LED2 (Anode) through 220Ω Resistor |
 | GPIO7 | LED3 (Anode) through 220Ω Resistor |
 | GPIO8 | LED4 (Anode) through 220Ω Resistor |
 | GPIO9 | Button1 (One side) |
 | GPIO10 | Button2 (One side) |
 | GND | LED1, LED2, LED3, LED4 (Cathode) |
 | GND | Buttons (Other side) |
 | VIN | Breadboard Power Rail (+) |
 | GND |  Breadboard Power Rail (-) |

 **Circuit diagram:**

![WhatsApp Image 2024-07-12 at 19 54 06_bb2ec4a5](https://github.com/user-attachments/assets/2bb3721f-babe-4938-9165-1489141b3c22)

 **How to program:**

```
 #include <stdio.h>
#include <stdint.h>
#include "vsd_gpio.h" 

#define LED1_PIN 5
#define LED2_PIN 6
#define LED3_PIN 7
#define LED4_PIN 8
#define BUTTON1_PIN 9
#define BUTTON2_PIN 10

void setup() {
    gpio_set_direction(LED1_PIN, GPIO_OUTPUT);
    gpio_set_direction(LED2_PIN, GPIO_OUTPUT);
    gpio_set_direction(LED3_PIN, GPIO_OUTPUT);
    gpio_set_direction(LED4_PIN, GPIO_OUTPUT);
    
    gpio_set_direction(BUTTON1_PIN, GPIO_INPUT);
    gpio_set_direction(BUTTON2_PIN, GPIO_INPUT);
}

void loop() {
    int button1_state = gpio_read(BUTTON1_PIN);
    
    int button2_state = gpio_read(BUTTON2_PIN);
    
    if (button1_state == GPIO_HIGH) {
        gpio_write(LED1_PIN, GPIO_HIGH); 
        gpio_write(LED2_PIN, GPIO_LOW);  
    } else {
        gpio_write(LED1_PIN, GPIO_LOW);  
        gpio_write(LED2_PIN, GPIO_HIGH); 
    }
    
    if (button2_state == GPIO_HIGH) {
        gpio_write(LED3_PIN, GPIO_HIGH); 
        gpio_write(LED4_PIN, GPIO_LOW);  
    } else {
        gpio_write(LED3_PIN, GPIO_LOW);  
        gpio_write(LED4_PIN, GPIO_HIGH); 
    }
}

int main() {
    setup();
    
    while (1) {
        loop();
    }
    
    return 0;
}
```
</details>
