# Introduction #

คัดลอกจาก : http://www.spicydog.org/board/index.php?topic=431.0

ที่มา : http://www.roboac.com/accelerometer-และ-gyroscope-ต่างกันอย่างไร.htm


# Details #

ทุกวันนี้อุปกรณ์ Sensor ต่างๆ เริ่มหาซื้อได้ในราคาทั่วไป เช่น GPS ในรถยนต์ หรือโมดูล GPRS ใช้ทำโทรศัพท์หรือว่าจะเป็น Ultrasonic ที่ใช้ทำ sensor จับวัตถุที่ท้ายรถยนต์

มี Sensor ชนิดนึง ที่ใช้วัดความเอียง นั้นก็คือ Accelerometer และ Gyroscope
มือใหม่หลายคนจะไม่เข้าใจถึงความแตกต่างระหว่าง Sensor สองชนิดนี้

![https://lh4.googleusercontent.com/-CgVMgFOj9j4/UKJnw_vSNRI/AAAAAAAAFNI/72WHX6L_UuE/s392/AccelerometerAndGyroscope1.jpg](https://lh4.googleusercontent.com/-CgVMgFOj9j4/UKJnw_vSNRI/AAAAAAAAFNI/72WHX6L_UuE/s392/AccelerometerAndGyroscope1.jpg)

## Accelerometer คืออะไร ? ##


ถ้าแปลตรงตัวก็คือ Acceleration + Meter หรือมิเตอร์ความเร่ง ตามนิยามก็คือ Sensor วัดความเร่งเพิ่มขึ้น หรือลดลง (ในหน่วย m/s2)
ตย. ความเร่งของแรงโน้มถ่วงก็คือ 9.8 m/s2 หรือ a (มาจาก Acceleration) นั่นเอง


โดยหลักการทำงาน ให้นึกถึงห้องสี่เหลี่ยมเล็กๆ ที่ทุกด้านของกำแพงจะมีสปริงติดอยู่
เวลาที่ห้องนี้เอียงไปทางใดทางหนึ่ง สปริงก็จะยุบไปด้านนั้นๆ โดยติ๊ต่างว่าแรงดันของสปริงมีน้อยกว่าแรงโน้มถ่วงของโลก
และใช้วงจรไฟฟ้าในการดึง Output Analog ออกมาใช้งาน (หรือ Output Digital ซึ่งก็แล้วแต่ตัว Sensor เอง)

![https://lh3.googleusercontent.com/-6S0dS2SUqnM/UKJnwtaOEFI/AAAAAAAAFNU/ZFJpmVjjVMI/s223/AccelerometerAndGyroscope2.jpg](https://lh3.googleusercontent.com/-6S0dS2SUqnM/UKJnwtaOEFI/AAAAAAAAFNU/ZFJpmVjjVMI/s223/AccelerometerAndGyroscope2.jpg)

ราจะใช้ Accelerometer สำหรับเป็นตัวชี้ว่าอยู่ในสถานะ Static (นิ่งเฉย) หรือ Dynamic (เคลื่อนไหวทันทีทันใด หรือหยุดทันทีทันใด) นั่นทำให้ Accelerometer เป็น sensor สำหรับบอกสถานะการเอียงได้เป็นอย่างดี (Tilt Sensor)

Sensor พวกนี้ทำอะไรได้บ้าง ถ้ามองใกล้ๆ ตัวก็คือ iPhone ของพี่ๆ น้องๆ นี้แหละครับ


## แล้ว Gyroscope คืออะไร ? ##

Sensor Gyro จะทำหน้าที่วัดความเร็วเชิงมุม ก็คือโอเมก้าในวิชาฟิสิกส์ นี้แหละ (วัตถุนี้จะหมุนรอบแกนด้วยความเร็วเท่าใด ?) พูดด้วยนิยามอาจจะไม่เข้าใจว่าต่างกันอย่างไร


![https://lh6.googleusercontent.com/-TbokqU13oJ8/UKJnwxHcTeI/AAAAAAAAFNQ/hICkw9HVHic/s467/AccelerometerAndGyroscope3.jpg](https://lh6.googleusercontent.com/-TbokqU13oJ8/UKJnwxHcTeI/AAAAAAAAFNQ/hICkw9HVHic/s467/AccelerometerAndGyroscope3.jpg)

ยกตัวอย่าง ถ้าเราจับ Accelerometer มาเอียงแล้ววัด Output เราจะได้ค่า ค่านึงซึ่งบ่งบอกถึงการเอียงในรูปแบบนั้นๆ ถ้าเราเปลี่ยนไปค่านี้ก็จะเปลี่ยนตาม
แต่ถ้าเราจับ Gyro มาเอียงแล้ววัด Output เราจะพบว่า Output ของ Gyro จะออกก็ต่อเมื่อเกิดการเอียง หรือกำลังจะเอียง หรือเกิดการเคลื่อนไหว (วัตถุอยู่นิ่ง Gyro วัดค่าไม่ได้ เพราะไม่มีความเร็ว)


## แล้ว Gyro มีบทบาทอย่างไร ? ##

ในเมื่อ Accelerometer สามารถวัดความเอียงได้เรียบร้อย ไม่มีความจำเป็นจะต้องวัดความเร็วเชิงมุม ?
เพราะว่า Output ของ Accelerometer มีผลกับแรงโน้มถ่วง นั่นหมายถึงค่า Output ของ Accelerometer ไม่มีทางหยุดนิ่งเฉย แม้ปล่อยทิ้งไว้ มันก็จะวิ่งขึ้นๆ ลงๆ สั่นไปสั่นมา ต่างกับ Gyro ที่ปล่อยทิ้งไว้ค่า Output ที่ได้ก็จะนิ่ง ไม่เกิดการสั่น
และถ้าเรานำ Output ของ Gyro มาใช้กรรมวิธีการ Discrete Integral ก็จะสามารถหามุมได้ (เพราะ Output ของ Gyro เป็นความเร็วเชิงมุม)


ส่วนกรรมวิธีในการ Integral ใน MCU เราจะใช้ Discrete Integral ผมชอบพูดว่าเป็นการอินทิเกรตมือ หลักการคล้ายๆ กับการคูณใน MCU


การคูณใน MCU ทำได้โดยการบวก ไปจนครบจำนวนครั้ง การอินทิเกรตก็เหมือนกัน ให้มองกลับไปที่รากฐานการอินทิเกรต ถ้ามีกราฟมาให้มันก็คือพื้นที่ใต้กราฟ เราจะอินทิเกรตเราทำได้โดยแบ่งพื้นที่ใต้กราฟเป็นเส้นเล็กๆ แล้วหาพื้นที่เล็กๆ นั้น จากนั้นก็จับมารวมกัน


ถ้าเราแบ่งพื้นที่เล็กๆ นั้นด้วยเวลา t0, t1, t2, tn
นั่นก็คือเอาพื้นที่ ที่เวลา t0 มารวมกับพื้นที่ ที่เวลา t1 เอาพื้นที่ไปรวมกับพื้นที่ที่เวลา t2 ไล่ไปเรื่อยๆ ถึง tn โดยไม่สนใจว่าพื้นที่นั้นมีค่าเป็นบวกหรือลบ สุดท้ายแล้วคำตอบจะบอกเราเองว่าผลลัพท์ที่ได้ ชี้ไปในทิศทางใด


นี้เป็นสาเหตุให้เกิดการผสมผสานระหว่าง Sensor สองตัวนี้ ทำให้มีทฤษฎีมารองรับมากมาย อธิเช่น Kalman Filter, Complementary Filter ใช้การผสมผสานข้อดีของทั้งสอง Sensor

คัดลอกจาก : http://www.spicydog.org/board/index.php?topic=431.0

ที่มา : http://www.roboac.com/accelerometer-และ-gyroscope-ต่างกันอย่างไร.htm