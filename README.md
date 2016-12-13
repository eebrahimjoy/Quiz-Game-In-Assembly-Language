# Quiz-Game-In-Assembly-Language
.model small
.stack 100h
.data 

ms db " ********** Quiz game over 6th semester (CSE) by Ebrahim Joy(DIU) ********** : $" 
ms1 db "!!!!!! Please Choose Your Course!!!!! : $"
ms2 db " Please press 'd' for Data Communication : $"
ms3 db " Please press 'n'  for Numerical methods : $" 
ms4 db " Please press 'm' for Microprocessor & Assembly Language : $"
ms5 db " Please press 'b' for Bio-Informatics : $"

msg db "Answer The Following Question, Until three mistake: $"  
msg1 db "1. Which two team was newly promoted BPL 2016?: $"
qsn1 db "a. Dhaka,Rajshahi            b. Khulna ,Rangpor      c. Khulna,Rajshahi: $"
rht1 db " Your answer is right: $"
wrn1 db " Your answer is wrong:$" 
msg2 db "2. BHE is ..... ?: $"
qsn2 db "a. D7-D0                     b. D15-D8               c. D21-D0 : $"  
msg3 db "3. In reset operation CS is ..... ?: $"
qsn3 db "a.FFFFH                       b.Empty                c. 0000H : $"   
msg4 db "4. In A17/S4, A16/S3 Adress (1,0) combination is .... ? : $"
qsn4 db "a. Data Segment              b. Code Segment         c. Stack Segment : $" 
msg5 db "5. Which register specifying ports in some IN and OUT operations? : $"
qsn5 db "a. DX                        b. BX                   c. AX : $" 
msg6 db "6.  Offset address relative to CS which one ..? : $"
qsn6 db "a. IP                        b. BP                   c. SP : $" 
msg7 db "7. 8088 is a 16 bit microprocessor with a/an ... bitdata bus : $"
qsn7 db "a. 16                        b. 8                    c. 32 : $" 
msg8 db "8. In maximum mode pull MN/MX logic is ... : $"
qsn8 db "a. 0                         b. 1                    c. both : $" 
msg9 db "9. Lock is an/a .... : $"
qsn9 db "a. Input                     b. Universal            c. Output : $"  
msg10 db "10. When IF=0 INTR is .... : $"
qsn10 db "a. Enabled                  b. Disabled             c. Unmasked : $"
msg11 db "11. The TEST pin is tested by .... instruction : $"
qsn11 db "a. READY                    b. LOCK                 c. WAIT : $"
msg12 db "12. In ADD/SUM instruction flag affect is .... : $"
qsn12 db "a. All                      b. None                 c. All except CF : $"
msg13 db "13. In LOOP instruction CX is ..... : $"
qsn13 db "a. Increment automatically  b. Remain Same          c. Decrement Automatically : $"
msg14 db "14.A Left Arithmetic Shift by n is equivalent to... : $" 
qsn14 db "a. Divide by 2^n             b. Multiplying by 2^n  c. Divide by 2  : $"
msg15 db "15. Which instruction, shifts each bit to the right : $"
qsn15 db "a. ROR                       b. ROL                  c. LAS : $"
msg16 db "16. In PUSH instruction ,SP is.... : $" 
qsn16 db "a. Increased by 2            b. Remain same          c. Decreased by 2 : $"


again db "Press 'y' if you want to play again :$" 
nagain db "Press 'n' if you don't want to play : $"
congrats db " Congratulation , You Completed The Game: $"
failled db " Sorry You failled, Be pateint & try again , You can : $"
                                                               

.code

main proc
    mov ax,@data
    mov ds,ax
    
    mov ah,9
    mov dx,offset ms
    int 21h 
    
    ag:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,9
    mov dx,offset ms1
    int 21h
    
  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
    mov dx,offset ms2
    int 21h
    
 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
    mov dx,offset ms3
    int 21h

   
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset ms4
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset ms5
    int 21h
    
   
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
     
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    mov ah,1
    int 21h
    
    
    cmp al,'d'
    je level1
    cmp al,'n'
    je level2
    cmp al,'m'
    je level3
    cmp al,'b'
    je level4
    
    jmp ext
    
    
    
    
     level3:
     
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
     
     
    
    mov ah,9
    mov dx,offset msg
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
     
    mov cx,0
    
    mov ah,9
    mov dx,offset msg1
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
     
    
    mov ah,9
    mov dx,offset qsn1
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1 
    int 21h
    cmp al,'c'
    je rt1
    jmp er1
    
    
    rt1:
    
  
    
    mov ah,9
    mov dx,offset rht1
    int 21h 
  
    
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    jmp lev2
    
    
    er1:
    
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    lev2:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
     
     mov ah,9
     mov dx,offset msg2
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn2
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'b'
    je rt2
    jmp er2
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt2:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev3
    
    
    
    er2:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    lev3:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    mov ah,9
     mov dx,offset msg3
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn3
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt3
    jmp er3
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt3:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev4
    
    er3:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    lev4:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    mov ah,9
     mov dx,offset msg4
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn4
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'b'
    je rt4
    jmp er4
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt4:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev5
    
    er4:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    lev5:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
       
    mov ah,9
     mov dx,offset msg5
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn5
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt5
    jmp er5
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt5:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev6
    
    er5:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    lev6:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    mov ah,9
     mov dx,offset msg6
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn6
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt6
    jmp er6
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt6:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev7
    
    er6:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    lev7:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    
    mov ah,9
     mov dx,offset msg7
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn7
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'b'
    je rt7
    jmp er7
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt7:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev8
    
    er7:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    lev8: 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
     mov dx,offset msg8
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn8
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt8
    jmp er8
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt8:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev9
    
    er8:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    lev9:
    
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,9
     mov dx,offset msg9
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn9
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'c'
    je rt9
    jmp er9
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt9:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev10
    
    er9:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    
    lev10:
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    
    mov ah,9
     mov dx,offset msg10
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn10
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'b'
    je rt10
    jmp er10
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt10:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev11
    
    er10:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    
    lev11: 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
     mov dx,offset msg11
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn11
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'c'
    je rt11
    jmp er11
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt11:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev12
    
    er11:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    lev12:
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
     mov dx,offset msg12
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn12
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt12
    jmp er12
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt12:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev13
    
    er12:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    lev13:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    mov ah,9
     mov dx,offset msg13
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn13
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'c'
    je rt13
    jmp er13
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt13:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev14
    
    er13:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    
    lev14:
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    mov ah,9
     mov dx,offset msg14
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn14
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'b'
    je rt14
    jmp er14
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt14:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev15
    
    er14:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    
    
    lev15:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    mov ah,9
     mov dx,offset msg15
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn15
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'a'
    je rt15
    jmp er15
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt15:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp lev16
    
    er15:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit
     
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    lev16:
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    
    mov ah,9
     mov dx,offset msg16
     int 21h
     
     mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset qsn16
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,1
    int 21h
    cmp al,'c'
    je rt16
    jmp er16
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    rt16:
    
    mov ah,9
    mov dx,offset rht1
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    jmp pass
    
    er16:
    
    mov ah,9
    mov dx,offset wrn1
    int 21h
    inc cx
    cmp cx,3
    je exit
    jmp pass 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
            
            
    
    
    
    exit: 
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    mov ah,9
    mov dx,offset failled
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h  
    
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h 
    
    
    mov ah,9
    mov dx,offset again
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,9
    mov dx,offset nagain
    int 21h 
    
    
    mov ah,1
    int 21h
    cmp al,'y'
    je ag 
    cmp al,'n'
    je ext
    
    jmp ext
    
    
    pass: 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    
    
    mov ah,9
    mov dx,offset congrats
    int 21h  
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,9
    mov dx,offset again
    int 21h 
    
    mov ah,2
    mov dl,0ah
    int 21h
    mov dl,0dh
    int 21h
    
    mov ah,9
    mov dx,offset nagain
    int 21h
    
    
    mov ah,1 
    int 21h
    cmp al,'y'
    je ag
    cmp al,'n'
    je ext
     
    
    
    
    level1:
    
    
    level2:
    
    
    level4:
    
    
    
    
    ext:
    
    main endp
end main
