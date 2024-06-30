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
After using the command you will get the complex assembly output.

To get the exact assembly output of your code, use the command
    
```
    riscv64-unknown-elf-objdump -d sum1ton.o | less
```

And finally search the main using ```\main```

Hence, you will get the final output of this task as 

![calculations of instructions](https://github.com/VasanthKumar-05/vsdsquadron/assets/173717586/059d35ea-d38b-46cb-a276-20b81dde9fb9)

      
