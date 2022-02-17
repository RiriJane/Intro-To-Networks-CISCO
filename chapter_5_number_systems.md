**These notes are taken from courses in Cisco Networking Academy. No copyright intended**

#Chapter 5 - Number Systems

##5.1 Binary Number System 
###5.1.1 Binary and IPv4 Addresses
- IPv4 addresses begin as binary and are converted to decimal for easier management.
  - **Binary numbering system** : consists of 0s and 1s called **bits**, base 2.
  - **Decimal numbering systems** : consists of numbers from 0 to 9, base 10.
- Hosts, servers and network devices uses binary addressing

**Binary IPv4 addresses**
![Binary IPv4 Addresses](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/binary_ipv4_address.jpg)

- Each address consist of a string of 32 bits, divided into 4 sections called octets.
- Each octet contains 8 bits (1 byte), separated with a dot.
- For example :
  - PC1 IPv4 address: 11000000.10101000.00001010.00001010
  - PC1 default gateway address (R1 Gigabit Ethernet interface): 11000000.10101000.00001010.00000001
- **Dotted decimal notation** : binary address converted for easier read. For example :
  - PC1 IPv4 address : 192.168.10.10
  - PC1 default gateway : 192.168.10.1

![Dotted decimal notation](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/dotted_decimal_notation.jpg)

###5.1.2 Converting Between Binary and Decimal Numbering Systems
####Positional Notation or place values
**Place values of decimal numbering systems**

![Place values of decimal numbering systems](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/place_values_decimal.jpg)

- Base 10 number system (0,1,2,3,4,5,6,7,8,9)
- Place values of 2,1,6 and 8:
  - 2 in the thousand's place (2 x 1'000 = 2'000)
  - 1 in the 100's place (1 x 100 = 100)
  - 6 in the tenth's place (6 x 10 = 60)
  - 8 in the one's place (8 x 1 = 8)
  - Adding all this up is a total of 2'168
- Place values are based on powers to ten
  - one's place is ten to the 0 
  - ten's place is ten to the 1 (10 x 1 = 10)
  - hundred's place is ten to the 2 (10 x 10 = 100)
  - thousand's place is ten to the 3 (10 x 10 x 10 = 1'000)
  - etc. 


**Place values of binary number systems**

![Place value of binary number systems](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/plac_values_binary.jpg)

- Base 2 number system (0,1)
- Place values :
  - one's place 
  - 2's place (2 x 1 = 2)
  - 4's place (2 x 2 = 4)
  - 8's place (2 x 2 x 2 = 8)
  - etc.
- There are 8 place values because we need 8 bits for the addresses

![168 in binary](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/168_in_binary.jpg)

**Converting decimal number to binary (168 to binary)** :
- Starting at the left side, if the place value have 1 under it, it means that you need this number to enable to reach 168.
- If the number is 0 under the place value, it's not addition
- In total, 128 + 32 + 8 is equal to 168
- 168 in binary is 10101000

![Binary to decimal conversion ](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/binary_decimal_conversion.jpg)

**Converting binary to decimal (01101101)** :
- Add all up the numbers that have 1 underneath
- 64 + 32 + 8 + 4 + 1 = 109

####Converting binary address to dotted decimal notation 

![Binary address to dotted decimal notation conversion](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/binary_address_to_dotted_decimal_notation.jpg)

- 1st octet : 128 + 64 = 192
- 2nd octer : 128 + 32 + 8 = 168
- 3rd octet : 1
- 4th octet : 64 + 32 + 4 + 1 = 101

###5.1.7 Positional Notation Process

![Positional Notation Process](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/positional_notation_process.jpg)

Convert 192.168.11.10. The steps :
1. Is 192 >= 128 ? Yes. Add 1 to 128's place.
2. Substract 128 to 192. 192 - 128 = 64.
3. Is 64 >= 64 ? Yes. Add 1 to 64's place.
4. Substract 64 to 64. 64 - 64 = 0.
5. Is 0 >= 32 ? No. Add 0.
6. Continue until the one's place is reached.
7. Continue until each decimals are converted.

###5.1.11 IPv4 Addresses

**Dotted Decimal Address** - an Ipv4 address assigned to a device

![Dotted Decimal Address](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/dotted_decimal_address.jpg)

**Octets** - Addresses are made up of 4 octets

![Octets](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/octets.jpg)

**32-bit address** - the computer stores the address as the entire 32-bit data stream

![32-bit address](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/32-bit_address.jpg)

##5.2 Hexadecimal Number
###5.2.1 Hexadecimal and IPv6 Addresses

![decimail, binary, hexadecimal equivalence table](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/equivalence_table.jpg)

- Hexadecimal is a base 16 system (0 to 9 and A to F).
- Powers of 16.
- Represents IP version 6 addresses and Ethernet MAC addresses.
- 1Pv6 addresses are 128 bits in length.
- Every 4 bits (4-bit binary number) is represented by a single hexadecimal digit, for a total of 32 hexadecimal values.
- Hextet is an unofficial term that refers to a segment of 16 bits (4 hexadecimal values).


###5.2.2 Converting between Hexadecimal and Decimal Numbering Systems

![Hexadecimal place value table](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/hexadecimal_place_values.jpg)

**Converting hex 2A to decimal**

![Hex 2A to decimal](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/converting_2A_to_decimal.jpg)

- Write 2A in their respective position (A in one's place and 2 in 16's place)
- Multiply each hex symbol by the place value 
  - A x 1 = 10 (in decimal)
  - 2 x 16 = 32
- Addition all . 10 + 32 = 42 decimal

**Converting Decimal 197 to hex (by decimal)**
- It's mostly easier to decimal to binary first then to hex 
- Convert decimal to 8-bit binary : 11000101 (197)
- Convert binary to decimal

![Binary to hex](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/binary_11000101_hex.jpg)

- Split the 8-bit binary to two 4-bit binary numbers
- Write down each binary number to its respective place value
- Convert each half to decimal
- Convert each decimal to it's corresponding hex value
- 197 decimal = C5 hex or 0xC5


**Converting 9F hex to decimal (by binary)**

![Direct conversion hex to decimal](https://github.com/RiriJane/Intro_To_Networks_CISCO/blob/main/images/chap5/direct_conversion_hex_decimal.jpg)

- Convert each hex symbol to 4-bits binary equivalent
- Combine into one 8-bit binary number 
- Convert to decimal



























