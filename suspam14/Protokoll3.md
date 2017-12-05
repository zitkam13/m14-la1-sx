12: {
00000040 cf.93                PUSH R28		Push register on stack  
00000041 df.93                PUSH R29		Push register on stack   
>Pushed Register vom Stack
>R26 bis R31 dürfen bei Funktionsaufruf nicht verändert werden  

00000042 1f.92                PUSH R1		Push register on stack  
>erhöht Stackpointer um 1 -> definition von Variable  

00000043 cd.b7                IN R28,0x3D		In from I/O location  
00000044 de.b7                IN R29,0x3E		In from I/O location  
>Lädt Stackpointer in Y-Register

14: 	x=10+23;
00000045 81.e2                LDI R24,0x21		Load immediate 
00000046 89.83                STD Y+1,R24		Store indirect with displacement 
>wegen volatile  

15: 	return x;
00000047 89.81                LDD R24,Y+1		Load indirect with displacement 

    16: }
00000048 90.e0                LDI R25,0x00		Load immediate 
00000049 0f.90                POP R0		Pop register from stack 
0000004A df.91                POP R29		Pop register from stack 
0000004B cf.91                POP R28		Pop register from stack 
0000004C 08.95                RET 		Subroutine return 

```
int main(void)
{
	volatile unsigned char a=10;  
	volatile unsigned char b=20;  
	volatile int e=a+b;  
	return e;  
}
```

12: {
00000040 cf.93                PUSH R28		Push register on stack  
00000041 df.93                PUSH R29		Push register on stack  
00000042 00.d0                RCALL PC+0x0001		Relative call subroutine  
00000043 00.d0                RCALL PC+0x0001		Relative call subroutine  
>Macht Platz am Stack  

00000044 cd.b7                IN R28,0x3D		In from I/O location  
00000045 de.b7                IN R29,0x3E		In from I/O location  
>Y=SP  
    13: 	volatile unsigned char a=10;  
00000046 8a.e0                LDI R24,0x0A		Load immediate   
00000047 89.83                STD Y+1,R24		Store indirect with displacement  
    14: 	volatile unsigned char b=20;
00000048 84.e1                LDI R24,0x14		Load immediate  
00000049 8a.83                STD Y+2,R24		Store indirect with displacement  
    15: 	volatile int e=a+b;
0000004A 29.81                LDD R18,Y+1		Load indirect with displacement  
0000004B 8a.81                LDD R24,Y+2		Load indirect with displacement  
0000004C 90.e0                LDI R25,0x00		Load immediate  

0000004D 82.0f                ADD R24,R18		Add without carry  
0000004E 91.1d                ADC R25,R1		Add with carry  
>R18 + R24 = R25  

0000004F 9c.83                STD Y+4,R25		Store indirect with displacement  
00000050 8b.83                STD Y+3,R24		Store indirect with displacement  
>speichert R25 am Stack 

    16: 	return e;
00000051 8b.81                LDD R24,Y+3		Load indirect with displacement  
00000052 9c.81                LDD R25,Y+4		Load indirect with displacement  
    17: }
00000053 0f.90                POP R0		Pop register from stack 
00000054 0f.90                POP R0		Pop register from stack 
00000055 0f.90                POP R0		Pop register from stack 
00000056 0f.90                POP R0		Pop register from stack 
00000057 df.91                POP R29		Pop register from stack 
00000058 cf.91                POP R28		Pop register from stack
> Leert Stack
