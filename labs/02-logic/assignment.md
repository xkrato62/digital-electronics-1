# Lab 2: Dušan Kratochvíl

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](images2/Bhigher.jpg)

   Less than:

   ![K-maps](images2/Blower.jpg)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](images2/rov.be.low.hr.jpg)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **230276**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case
        s_b <= "0111"; 
        s_a <= "0110";     
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination 0111,0110 FAILED" severity error;
        
         -- second test case
        s_b <= "1111"; 
        s_a <= "0111";     
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination 1111,0111 FAILED" severity error;
        
        
         -- Third test case
        s_b <= "0110"; 
        s_a <= "1110";     
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        report "Input combination 0110,1110 FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure](images2/report2.png)

3. Link to your public EDA Playground example:

  https://www.edaplayground.com/x/j23w
