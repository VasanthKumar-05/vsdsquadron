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
