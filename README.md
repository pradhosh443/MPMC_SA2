# MPMC_SA2
# 8086 program to find the largest number

## AIM
Write an assembly language program in 8086 to find the largest number from a given set of N numbers stored in memory. Display the result in AL register.

---
## APPARATUS REQUIRED
- Personal Computer  
- Masm software

---
## Algorithm
1.Initialize pointer to the array header (SI points to the first byte: N).
2.Read N from [SI]. If N = 0 then terminate (nothing to process).
3.Increment SI to point to the first array element. Load that element into AL — this is the current maximum.
4.Decrement the element-count (we already consumed one). If count = 0 then go to termination (AL already holds the largest).
5.Loop: increment SI to point to next element, load the element into BL, compare BL with AL. If BL > AL then move BL → AL (update current maximum).
6.Decrement the remaining-count. If remaining-count > 0 repeat step 5.
7.Terminate: AL contains the largest value. Return to DOS (INT 21h / AH = 4Ch) or finish as required.

---
## PROGRAM

```
code segment
assume cs:code, ds:code
org 1000h
mov si,1200h
mov cl,[si]
inc si
mov al,[si]
dec cl
jz done
next: inc si
mov bl,[si]
cmp al,bl
jae skip
mov al,bl
skip: dec cl
jnz next
done: mov ah,4ch
int 21h
code ends
end
```
---
## OUTPUT:

<img width="641" height="431" alt="Screenshot 2025-10-24 212739" src="https://github.com/user-attachments/assets/a349f74d-6c27-4b2b-a3dc-2408db489054" />


---

## RESULT:
Thus, Assembly language program in 8086 to find the largest number from a given set of N numbers stored in memory and Displaying the result in AL register is successfully executed.
