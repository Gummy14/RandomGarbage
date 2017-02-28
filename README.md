/*
* lab2p2.asm
* Bubble Sort Table
* Created: 2/28/2017
* Author: Alex Helm
*/
		.dseg
		.org 0x2000
output: .byte 1						;student comment goes here
		.cseg
		.org	0x0
		jmp		main				;partial vector table at address 0x0
		.org	0x200				;MAIN entry point at address 0x200 (step through the code)
main:	

		ldi		ZL,low(2*table)		;returns twice the low byte of the table
		ldi		ZH,high(2*table)	;returns twice the high byte of the table
		ldi		r16,count			;student comment goes here
		add		ZL,r16				;student comment goes here
		ldi		r16,0				;student comment goes here
		adc		ZH,r16				;student comment goes here
		lpm r0, Z						;lpm = lpm r0,Z in reality, what does this mean?

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+1				
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r1, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r18,count+2				
		add		ZL,r18				
		ldi		r18,0			
		adc		ZH,r18				
		lpm r2, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r19,count+3				
		add		ZL,r19				
		ldi		r19,0			
		adc		ZH,r19				
		lpm r3, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r20,count+4			
		add		ZL,r20				
		ldi		r20,0			
		adc		ZH,r20				
		lpm r4, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r21,count+5			
		add		ZL,r21				
		ldi		r21,0			
		adc		ZH,r21				
		lpm r5, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r22,count+6			
		add		ZL,r22				
		ldi		r22,0			
		adc		ZH,r22				
		lpm r6, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r23,count+7			
		add		ZL,r23				
		ldi		r23,0			
		adc		ZH,r23				
		lpm r7, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r24,count+8			
		add		ZL,r24				
		ldi		r24,0			
		adc		ZH,r24				
		lpm r8, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r25,count+9			
		add		ZL,r25				
		ldi		r25,0			
		adc		ZH,r25				
		lpm r9, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r16,count+10		
		add		ZL,r16				
		ldi		r16,0			
		adc		ZH,r16				
		lpm r10, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r16,count+11		
		add		ZL,r16				
		ldi		r16,0			
		adc		ZH,r16				
		lpm r11, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+12		
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r12, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+13		
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r13, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+14		
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r14, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+15		
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r15, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r17,count+16		
		add		ZL,r17				
		ldi		r17,0			
		adc		ZH,r17				
		lpm r16, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r20,count+17		
		add		ZL,r20				
		ldi		r20,0			
		adc		ZH,r20				
		lpm r17, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r20,count+18		
		add		ZL,r20				
		ldi		r20,0			
		adc		ZH,r20				
		lpm r18, Z

		ldi		ZL,low(2*table)		
		ldi		ZH,high(2*table)
		ldi		r20,count+19		
		add		ZL,r20				
		ldi		r20,0			
		adc		ZH,r20				
		lpm r19, Z

checker:
		cp r1,r0
		brlt putbehind10
		cp r2,r1
		brlt putbehind21
		cp r3,r2
		brlt putbehind32
		cp r4,r3
		brlt putbehind43


	jmp checker2


		;sts		output,r0			;store look-up result to SRAM
		ret							;consider MAIN as a subroutine to return from - but back to where??
putbehind10:mov r21, r1
		mov r22, r0

		sts output,r21
		sts output+1, r22

		ldi r21, 1
		ldi r22, 0

		mov r26, r0
		mov r0, r1
		mov r1, r26

		mov r26, r22 

		jmp checker

putbehind21:
		mov r21, r2
		mov r22, r1

		sts output+1,r21
		sts output+2, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r1
		mov r1, r2
		mov r2, r26

		mov r26,r22 

		jmp checker

putbehind32:
			mov r21, r3
		mov r22, r2

		sts output+2,r21
		sts output+3, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r2
		mov r2, r3
		mov r3, r26

		mov r26,r22 

		jmp checker

putbehind43:
			mov r21, r4
		mov r22, r3

		sts output+3,r21
		sts output+4, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r3
		mov r3, r4
		mov r4, r26
		mov r26,r22 

		jmp checker


checker2:
		cp r5,r4
		brlt putbehind54
		cp r6,r5
		brlt putbehind65
		cp r7,r6
		brlt putbehind76
		cp r8,r7
		brlt putbehind87
		cp r9, r8
		brlt putbehind98

		jmp checker3
putbehind54:
			mov r21, r5
		mov r22, r4

		sts output+4,r21
		sts output+5, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r4
		mov r4, r5
		mov r5, r26
		mov r26,r22 

	jmp checker
putbehind65:
			mov r21, r6
		mov r22, r5

		sts output+5,r21
		sts output+6, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r5
		mov r5, r6
		mov r6, r26
		mov r26,r22 

	jmp checker
putbehind76:
			mov r21, r7
		mov r22, r6

		sts output+6,r21
		sts output+7, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r6
		mov r6, r7
		mov r7, r26
		mov r26,r22 

	jmp checker
putbehind87:
			mov r21, r8
		mov r22, r7

		sts output+7,r21
		sts output+8, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r7
		mov r7, r8
		mov r8, r26
		mov r26,r22 
		jmp checker
putbehind98:
			mov r21, r9
		mov r22, r8

		sts output+8,r21
		sts output+9, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r8
		mov r8, r9
		mov r9, r26
		mov r26,r22
		jmp checker 

checker3:
		cp r10,r9
		brlt putbehind109
		cp r11,r10
		brlt putbehind1110
		cp r12,r11
		brlt putbehind1211
		cp r13,r12
		brlt putbehind1312
		cp r14,r13
		brlt putbehind1413

		jmp checker4
putbehind109:
			mov r21, r10
		mov r22, r9

		sts output+9,r21
		sts output+10, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r9
		mov r9, r10
		mov r10, r26
		mov r26,r22
		jmp checker 

putbehind1110:
		mov r21, r11
		mov r22, r10

		sts output+10,r21
		sts output+11, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r10
		mov r10, r11
		mov r11, r26
		mov r26,r22
		jmp checker 

putbehind1211:
		mov r21, r12
		mov r22, r11

		sts output+11,r21
		sts output+12, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r11
		mov r11, r12
		mov r12, r26
		mov r26,r22
		jmp checker 
putbehind1312:
		mov r21, r13
		mov r22, r12

		sts output+12,r21
		sts output+13, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r12
		mov r12, r13
		mov r13, r26
		mov r26,r22
		jmp checker
putbehind1413:
		mov r21, r14
		mov r22, r13

		sts output+13,r21
		sts output+14, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r13
		mov r13, r14
		mov r14, r26
		mov r26,r22
		jmp checker 

checker4:
		cp r15,r14
		brlt putbehind1514
		cp r16,r15
		brlt putbehind1615
		cp r17,r16
		brlt putbehind1716
		cp r18,r17
		brlt putbehind1817
		cp r19,r18
		brlt putbehind1918

		jmp ender

putbehind1514:
		mov r21, r15
		mov r22, r14

		sts output+14,r21
		sts output+15, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r14
		mov r14, r15
		mov r15, r26
		mov r26,r22
		jmp checker 

putbehind1615:
		mov r21, r16
		mov r22, r15

		sts output+15,r21
		sts output+16, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r15
		mov r15, r16
		mov r16, r26
		mov r26,r22
		jmp checker 
putbehind1716:
		mov r21, r17
		mov r22, r16

		sts output+16,r21
		sts output+17, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r16
		mov r16, r17
		mov r17, r26
		mov r26,r22
		jmp checker 
putbehind1817:
		mov r21, r18
		mov r22, r17

		sts output+17,r21
		sts output+18, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r17
		mov r17, r18
		mov r18, r26
		mov r26,r22
		jmp checker 
putbehind1918:
		mov r21, r19
		mov r22, r18

		sts output+18,r21
		sts output+19, r22

		ldi r21, 0
		ldi r22, 0

		mov r26, r18
		mov r18, r19
		mov r19, r26
		mov r26,r22
		jmp checker 
ender:
		
table:	.db 74, 45, 91, 35, 12, 38, 79, 1, 28, 78, 13, 52, 69, 43, 80, 19, 61, 97, 26, 9 ;Random number table
		.equ count = 0		;modify Celsius from 0 to 19 degrees for different results
		ldi r18, count
		.exit

