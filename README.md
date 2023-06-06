# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
#### Step 1:
Create module encoder and decoder.

#### Step 2:
Get inputs and outputs for encoders and decoders.

#### Step 3:
Perform "or" operation for encoder and "and" logic for decoders.

#### Step 4:
Perform RTL LOGIC and get waveform.

#### Step-5:
End the module.

### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Pravinrajj
RegisterNumber:  212222240080
*/
### Encoder
```
module EX8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
### Decoder
```
module EX8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```
### RTL LOGIC  
#### Encoder
![Screenshot (130)](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/bbe22232-0bd4-491f-be58-6daacae10a49)
#### Decoder
![Screenshot 2023-01-28 205527](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/57cd9920-4008-4146-bc86-1a4eda4a8bbe)

### TIMING DIGRAMS  
#### Encoder
![Screenshot (131)](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/abf933da-cf49-4801-bb8a-9ab4044bf27c)

#### Decoder
![Screenshot 2023-01-28 205802](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/cbd6dedb-a096-4070-adbc-fce0df2210d1)

### TRUTH TABLE 
#### Encoder
![encodertt](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/103e3bb7-e19a-400d-bcd9-14e6a5eb6c7e)
#### Decoder
![decodertt](https://github.com/Pravinrajj/Experiment-08-Encoders-and-decoders-/assets/117917674/f73a00ad-2389-46f5-9a12-0ccf31cfe013)


### RESULTS 
Thus the program to implement encoder and decoder using verilog is verified.
