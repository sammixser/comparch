# CN210
# computer-architecture
## MIPS Instruction format
 มี 3 ประเภท
 
**R-Format**

|Opcode | Rs  | Rt | Rd  | Shamt | Funct  |
| ----- | ----- | ----- | ----- | ----- | ----- |
| (6bit) | (5bit) | (5bit) | (5bit) | (5bit) | (6bit) |

<br> คำสั่งในประเภท R-Format เป็นคำสั่งที่ให้ในการคำนวณทางคณิตศาตร์ บวก ลบ คูณ หาร ฯลฯ

**I-Format**

| Opcode |  Rs   | Rt    | value or offset  |
| -----  | ----- | ----- | ----- |
| (6bit) | (5bit) | (5bit) | (16bit) | 

<br> คำสั่งใน I-Format เป็นคำสั่งที่ใช้ในการย้ายข้อมูล หรือ เคลื่อนที่ข้อมูลไปตำแหน่งที่ต้องการ

**J-Format**

| Opcode | Address |
| -----  | ----- |
| (6bit) | (26bit) |

<br> ตำสั่งใน J-Format เป็นคำสั่งให้ jump ไปทำงานที่ตำแหน่งที่ต้องการ

* [CLIP1](https://youtu.be/h8Iu4MPJTW8) คำสั่งการบวก
   <br>**สรุปเนื้อหา** การทำงานในคำสั่่งการบวกใน R-type นั้นประกอบด้วย register 3 ตัว คือ $1(rd), $2(rs), $3(rt) ซึ่งทั้ง 3 ตัวนี้มีหน้าที่ในการเก็บค่าของตัวเลขค่าหนึ่งๆ คำสั่งนี้มักจะเขียนอยู่ในรูป | **ADD $1, $2, $3** | การทำงานของคำสั่งนี้คือ นำ $2 ไปบวกกับ $3 แล้วนำผลลัพธ์ที่ได้มาเก็บลงใน $1

* [CLIP2](https://youtu.be/iNJk7NR0DzQ) การทำงานของ CPU
   <br>**สรุปเนื้อหา**

* [CLIP3](https://youtu.be/lI3voWLdYi0) ความแตกต่างระหว่าง multi-cycle และ single-cycle
   <br>**สรุปเนื้อหา**

* [CLIP4](https://youtu.be/jyjt2qI6w38) การทำงานของ multi-cycle ในคำสั่ง lw
   <br>**สรุปเนื้อหา**

* [CLIP5](https://youtu.be/2hWUXlziX20) การทำงานของ multi-cycle ในคำสั่ง beq
   <br>**สรุปเนื้อหา**

* [CLIP6](https://youtu.be/jrDffEOrVz0) การทำงานของคำสั่ง R-type ใน multi-cycle
   <br>**สรุปเนื้อหา**
