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
| (6bit)  | (5bit)|

<br> ตำสั่งใน J-Format เป็นคำสั่งให้ jump ไปทำงานที่ตำแหน่งที่ต้องการ

## Singlecycle Processor
![image](https://media.discordapp.net/attachments/258944901260115974/701424529032871976/image0.png?width=1026&height=412)
single-cycle เป็นกระบวนการทำงานที่ทำงานในคำสั่งหนึ่งๆให้จบภายใน 1 cycle หรือ 1 รอบ

## Multicycle Processor
![image](https://media.discordapp.net/attachments/258944901260115974/701426221803634758/image0.png?width=1026&height=410)
multi-cycle เป็นกระบวนกาทำงานในคำสั่งหนึ่งๆไม่จบใน 1 cycle หรือ 1 รอบ ใน multi-cycle นี้จะมีการทำงานในคำสั่งหนึ่งๆมากกว่า 1 รอบ และไม่เกิน 5 รอบ
![image](https://media.discordapp.net/attachments/258944901260115974/701426222093172792/image1.png?width=1026&height=432)

## RISC VS CISC
* **RISC (Reduced Instruction Set Computer)**
<br> เป็นคอมพิวเตอร์ที่มีคำสั่งน้อย ลดความซับซ้อนของวงจรเพื่อให้มีการทำงานที่เร็วขึ้น ทุกคำสั่งมีขนาดเท่ากันหมด
<br> -Multi register set
<br> -Single-clock cycle instructions
<br> -Highly pipelined
<br> -Program code size large
<br>**Harvard architecture** มี memory 2 ตัว เก็บคำสั่ง 1 ตัว และก็บข้อมูล 1 ตัว แยกกัน
<br>![image](https://media.discordapp.net/attachments/258944901260115974/701699446651486228/unknown.png?width=449&height=362)

* **CISC (Complex Instruction Set Computer)**
<br> เป็นคอมพิวเตอร์ที่มีชุดคำสั่งซับซ้อน แต่ละตำสั่งมีขนาดไม่เท่ากัน
<br> -Single register set
<br> -Multi-clock cycle instructions
<br> -Less to no pipelined
<br> -Program code size smalll
<br>**Von Neuman architecture** มี memory 1 ตัว เก็บทั้งคำสั่งและข้อมูล
<br>![image](https://media.discordapp.net/attachments/258944901260115974/701700512944226404/unknown.png?width=410&height=319)

## Pipelining
Instruction Pipelining คือ การใช้ pipelining เพื่อให้คำสั่งมากกว่าหนึ่งคำสั่งอยู่ในขั้นตอนของการดำเนินการในเวลาเดียวกัน กล่าวคือทำงานในคำสั่งถัดไปได้โดยที่ไม่ต้องรอให้คำสั่งก่อนหน้าเสร็จก่อน
<br>![image](https://media.discordapp.net/attachments/258944901260115974/701704890186989609/image.png?width=670&height=474)
<br>![image](https://media.discordapp.net/attachments/258944901260115974/701705047716921425/image.png?width=1002&height=474)

## LEARNING
* [CLIP1](https://youtu.be/h8Iu4MPJTW8) คำสั่งการบวก
   <br>**สรุปเนื้อหา** การทำงานในคำสั่่งการบวกใน R-type นั้นประกอบด้วย register 3 ตัว คือ $1(rd), $2(rs), $3(rt) ซึ่งทั้ง 3 ตัวนี้มีหน้าที่ในการเก็บค่าของตัวเลขค่าหนึ่งๆ คำสั่งนี้มักจะเขียนอยู่ในรูป <br> | **ADD $1, $2, $3** | <br>การทำงานของคำสั่งนี้คือ นำ $2 ไปบวกกับ $3 แล้วนำผลลัพธ์ที่ได้มาเก็บลงใน $1

* [CLIP2](https://youtu.be/iNJk7NR0DzQ) **การทำงานของ CPU**
   <br>**สรุปเนื้อหา** CPU จะทำงานโดยที่อาจเริ่มจากที่อยู่ addess(00000000) และนำคำสั่งเลขฐาน16 8bit มาแปลงเป็นเลขฐาน2 32bit และ CPU ก็จะดู opcode ว่าคำสั่งนี้เป็นคำสั่งให้ทำอะไร และก็จะทำงานตามคำสั่งนั้น พอทำงานในคำสั่งที่ทำอยู่เสร็จ CPU ก็จะทำการเริ่มทำงานในคำสั่งถัดไปเรื่อยๆ

* [CLIP3](https://youtu.be/lI3voWLdYi0) **ความแตกต่างระหว่าง multi-cycle และ single-cycle**
   <br>**สรุปเนื้อหา** 
   
| Multi-cycle | Single-cycle |
| -----  | ----- |
| -มี memory 1 ตัว  | -มี memory 2 ตัว |
| -มี ALU 1 ตัว  | -มี ALU 3 ตัว |
| -มีที่พักข้อมูล register A, B  | -None |
| -ทำงาน 1 คำสั่งหลาย cycle  | -ทำงานคำสั่งจบใน 1 cycle |

* [CLIP4](https://youtu.be/jyjt2qI6w38) **การทำงานของ multi-cycle ในคำสั่ง lw**
   <br>**สรุปเนื้อหา** เริ่มที่ T1: PC จะส่งคำสั่งเข้าไปเก็บที่ memory และ เข้าไปที่ instruction register และ นำ PC ไปบวกกับ 4 ที่ ALU และส่งค่า PC+4 ไปเก็บแทนที่ PC เดิม 
   <br> T2: นำ binaryตัวที่ 21-25 หรือเรียกว่า Rs ไปเก็บที่ register ตัวที่ 1 และนำ birany ตัวที่ 16-20 หรือ Rt ไปเก็บใน register ตัวที่ 2 และต่อมา นำbinary ตัวที่ 0-15 มาแปลงเป็น 32bit ไปที่ ALU เพื่อไปบวกกับ PC+4 และส่งค่าไปเก็บที่ ALUOut
   <br> T3: นำbinaryตัวที่ 0-15 ที่เราแปลงเป็น 32bit ไปบวกกับ register ตัวที่ 1 
   <br> T4: นำค่าที่อยู่ที่ ALUOut ส่งที่เก็ยที่ MemoryDataRegister 
   <br> T5: นำค่าที่เก็บไว้ใน MemoryDataRegister ไปเก็บที่ register ตัวที่ 2
   
* [CLIP5](https://youtu.be/2hWUXlziX20) **การทำงานของ multi-cycle ในคำสั่ง beq**
   <br>**สรุปเนื้อหา**

* [CLIP6](https://youtu.be/jrDffEOrVz0) **การทำงานของคำสั่ง R-type ใน multi-cycle**
   <br>**สรุปเนื้อหา**

* [CLIP7](https://youtu.be/kUqOY8FeYDo) **การทำงานของ Pipelining**
   <br>**สรุปเนื้อหา** การทำงานของ Pipelining CPU จะทำงานหลานคำสั่งพร้อมๆกัน โดยแต่ละขั้นตอนจะมีการคาบเกี่ยวกัน
   <br>![image](https://media.discordapp.net/attachments/258944901260115974/701708095713443890/unknown.png?width=468&height=96)
   <br>จากภาพ มีการทำงาน 2 คำสั่งพร้อมๆกัน โดยที่คำสั่งแรกทำงานในขั้นตอน Fetch พอทำงานในขั้นตอนนี้เสร็จก็ส่งไปทำงานในขั้นตอนของ Dcd และ Fetch ก็จะว่าง CPU จะมีการนำคำสั่งถัดไปมาทำงานในขั้นตอนของ Fetch และจะทำงานคาบเกี่ยวกันไปจนจบการทำงาน
