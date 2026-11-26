API รายการสินค้า
สถานะ: PROPOSED
รุ่น: v1
เจ้าของข้อเสนอ: microsevices
คำขอ: GET /api/v1/catalog/products
Request body: ไม่ส่ง
Query: available เลือกใส่ได้ รับ true หรือ false

{
  "field": [
    { "id": "pencil", "name": "ดินสอ", "priceSatang": 1200, "available": true },
    { "id": "ruler", "name": "ปากกาสีน้ำเงิน", "priceSatang": 2000, "available": false }
     { "id": "eraser", "name": "ยางลบ", "priceSatang": 800, "available": true },
    { "id": "pesharpener", "name": "กบเหลาดินสอ", "priceSatang": 1500, "available": false }
  ]
}

queryที่ส่ง           status   response body               เหตุผล
avalible=true       200     dataมีดินสอ 2 รายการ          มีดินสอ2รายการ    
avalible=false      404     ไม่มีรายการสินค้า               ไม่มีรายการสินค้า
avalible='  '       200     ได้รับสินค้าทั้งหมด               ไม่ได้กำหนดสินค้าไว้
avalible=yes        422     ค่าควรเป็นtrueหรือfalse        avaliable ไม่เป็น true false

กรณีที่ส่ง ส่ง avalible ? ข้อมูลผิดรูปแบบ เพราะส่งค่าavalible เป็นอย่างอื่นที่ไม่ใช่ true or false