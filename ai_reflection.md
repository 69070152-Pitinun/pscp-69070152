# บันทึก Reflection การใช้ AI

ใช้ไฟล์นี้เฉพาะเมื่อมีการใช้ AI กับโจทย์ OJ ที่เป็น learning-log-required เท่านั้น

ให้ copy template นี้ แล้วเปลี่ยนชื่อไฟล์เป็น:

```text
ai_reflection.md
```

เขียน reflection นี้ด้วยคำพูดของตนเอง

ห้ามวาง AI conversation ทั้งหมด

ห้ามให้ AI เขียน reflection นี้แทนคุณ

AI อาจช่วยตรวจ grammar, formatting หรือความชัดเจนได้ หลังจากที่คุณเขียน reflection ของตนเองแล้ว

---

## 1. ข้อมูล OJ

| Item | Answer |
| OJ problem number/title | OJ3011 - Colors |
| OJ submission ID, if submitted | 545178 |
| OJ status | Pass |

---

## 2. เครื่องมือ AI ที่ใช้

เขียนชื่อเครื่องมือ AI ที่ใช้

ตัวอย่าง:

```text
ChatGPT
Claude
Gemini
ChatGPT Codex / OpenAI Codex / Codex CLI
Claude Code
Other: ...
```

My answer:

```text
Gemini
```

---

## 3. การตรวจสอบนโยบายการใช้ AI ของรายวิชา

ตอบหัวข้อนี้อย่างซื่อสัตย์

หัวข้อนี้ยืนยันว่าคุณได้ทำตาม AI workflow ของรายวิชาก่อนและระหว่างใช้ AI

| Statement | Yes / No / Not Applicable | Short note |
|---|---|---|
| I read the relevant workflow before using AI. | Yes |  |
| I used `instructions/COURSE_AI_INSTRUCTIONS.md`, `instructions/AGENTS.md`, or manually followed the course AI instructions if the tool did not support custom instructions. | Yes |  |
| I wrote my own problem understanding before asking AI for help. | Yes |  |
| I wrote my own first plan before asking AI for help. | Yes |  |
| I used AI as a coach, reviewer, debugger, or test-case helper, not as a full-answer generator. | Yes |  |

ถ้าตอบ "No" ในข้อใด ให้อธิบายเหตุผล:

```text

```

---

## 4. ฉันถาม AI ให้ช่วยอะไร

อธิบายสั้น ๆ ว่าถาม AI ให้ช่วยเรื่องอะไร

ห้ามวาง chat log ทั้งหมด

ตัวอย่าง:

- ฉันถาม AI ให้ช่วยอธิบายโจทย์ด้วยภาษาที่เข้าใจง่ายขึ้น
- ฉันถาม AI ให้ช่วย review แผนแรกของฉัน
- ฉันถาม AI ให้ช่วยหา bug ใน code
- ฉันถาม AI ให้ช่วยเสนอ test cases
- ฉันถาม AI ให้อธิบายว่าทำไม output ของฉันต่างจาก expected output

My answer:

```text
ฉันขอคำใบ้จาก AI เรื่อง Bug ในโค้ด (เรื่องการใช้ and , or ในเงื่อนไข if-elif) และหลังจากที่ Debug เสร็จเรียบร้อยแล้วฉันก็ได้ขอให้ AI ช่วยอธิบายส่วนที่มันผิดให้เห็นภาพมากขึ้น
```

---

## 5. AI ช่วยให้ฉันสังเกตอะไร

เขียนว่า AI ช่วยให้คุณสังเกตอะไร

ตัวอย่าง:

- ความเข้าใจผิดเกี่ยวกับโจทย์
- condition ที่ขาดไป
- bug ในการอ่าน input
- edge case
- ปัญหา syntax ของ Python
- ปัญหา output formatting

My answer:

```text
AI ช่วยให้ฉันสังเกตการใช้ and และ or ในเงื่อนไข โดยในตอนแรกฉันได้สร้างเงื่อนไข 
(pri1,pri2 คือแม่สีที่รับค่ามาผสมกัน)

if (pri1 == "Yellow" or pri2 == "Red") and (pri1 == "Red" or pri2 == "Yellow"):
        print("Orange")

เมื่อรันโค้ดดังกล่าวส่งผลให้เมื่อป้อน"Yellow" และ "Blue" output ควรจะออกมาเป็น "Green" แต่ output กลับมาเป็น "Orange" 

หลังจากได้รับคำใบ้จาก AI เรื่องตำแหน่งของการใช้ and และ or จึงได้แก้โค้ดเป็น

if (pri1 == "Yellow" and pri2 == "Red") or (pri1 == "Red" and pri2 == "Yellow"):
        print("Orange")

ทำให้โค้ดสามารถรันได้ถูกต้อง และฉันได้ขอให้ AI ช่วยอธิบายเพิ่มเติมถึงสาเหตุที่รันโค้ดออกมาได้ค่าที่ไม่ถูกต้อง
และได้รู้ว่าในตอนแรกตนเองคิด logic ออกมาหละหลวมจนเกินไปทำให้เกิดช่องโหว่ การใช้ or ทั้งสองวงเล็บทำให้เมื่อเราป้อนค่า "Yellow" เข้ามา 2 ตัว โปรแกรมจะคำนวณออกมาเป็น

if (pri1 == "Yellow" or pri2 == "Red") and (pri1 == "Red" or pri2 == "Yellow"):
        print("Orange"

(pri1 == "Yellow" or pri2 == "Red") #วงเล็บที่ 1 มี "Yellow" - จะได้ค่า True 
(pri1 == "Red" or pri2 == "Yellow") #วงเล็บที่ 2 มี "Yellow" - จะได้ค่า True 

# True and True = True โปรแกรมจึง print ค่า "Orange" ออกมา ทำให้ไม่ผ่าน Testcase
```

---

## 6. ฉันตรวจสอบหรือแก้อะไรด้วยตนเอง

เขียนว่าหลังจากได้รับความช่วยเหลือจาก AI คุณตรวจสอบ ทดสอบ หรือแก้อะไรด้วยตนเอง

ตัวอย่าง:

- ฉันตรวจ input format ใน OJ problem อีกครั้ง
- ฉันทดสอบ code ใน VS Code
- ฉันเปรียบเทียบ expected output กับ actual output
- ฉันแก้ loop condition ด้วยตนเอง
- ฉันไม่ใช้บางคำแนะนำของ AI เพราะไม่ตรงกับ constraints ของโจทย์
- ฉันปรับคำแนะนำของ AI ให้เป็น code ที่ฉันเข้าใจเอง

My answer:

```text
ฉันกลับไปดู Testcase และพบว่าฉันคิดตกหล่นกรณีที่แม่สีทั้ง 2 สีที่รับค่ามาเป็นสีเดิม ฉันจึงเขียนเงื่อนไขเพิ่มลงไป และเมื่อสังเกตเพิ่มก็พบว่าตัวเองพิมพ์ Error เป็น error จึงได้ทำการแก้ไขให้เป็นไปตามที่โจทย์ต้องการ
```

---

## 7. ฉันได้เรียนรู้อะไร

เขียน 2-4 ประโยคเกี่ยวกับสิ่งที่ได้เรียนรู้จากโจทย์นี้และจากกระบวนการใช้ AI ช่วย

ให้เน้นการเรียนรู้ของตนเอง

ห้ามเขียนแค่ว่า "I learned coding" หรือ "AI helped me."

My answer:

```text
ฉันได้เรียนรู้ว่าควรจะเช็คความเรียบร้อยของโค้ดก่อนส่ง เพราะเรามักจะมองข้ามอะไรเล็ก ๆ น้อย ๆ เช่น ( Error เขียนผิดเป็น error ) และได้เรียนรู้การใช้ and และ or บางทีการเขียนโค้ดจากภาษามนุษย์ทันทีอาจทำให้โปรแกรมทำงานผิดพลาดและมีช่องโหว่ 
ตัวอย่าง กรณีของฉัน :
ถ้าแม่สีแรกเป็นสีเหลืองหรือแม่สีที่สองสีแดง และ ถ้าแม่สีแรกเป็นสีแดงหรือแม่สีที่สองเป็นสีเหลือง
ให้ส่งค่าสีส้ม

if (pri1 == "Yellow" or pri2 == "Red") and (pri1 == "Red" or pri2 == "Yellow"):
        print("Orange")

# ผลออกมา คือค่าที่ไม่ถูกต้องตาม Testcase จึงต้้องไปแก้ไขการทำงานของ and และ or

พอฟังเป็นภาษามนุษย์เราเข้าใจ แต่คอมพิวเตอร์มี logic การทำงานที่ชัดเจน ดังนั้นฉันจึงได้เรียนรู้ว่าการคิด logic นั้นควรคิดให้ละเอียด รอบคอบ และไม่หละหลวม
```

---

## 8. คำรับรองของนักศึกษา

ตอบอย่างซื่อสัตย์

| Statement | Yes / No |
|---|---|
| I wrote this reflection in my own words. | Yes |
| This reflection describes my real AI use. | Yes |
| I checked AI's suggestions before using them. | Yes |
| I can explain my final code. | Yes |
| I did not ask AI to write this reflection for me. | Yes |
