# APIs Documentation
------
### 1. ชื่อกลุ่มของเซอร์วิส : Accessories Services 
 

**คำอธิบาย** : กลุ่มของเซอร์วิสสำหรับบริการเสริมช่วยอำนวยความสะดวกให้กับแอพพลิเคชั่น เช่น บริการสร้างเอกสาร PDF, Email, Notification, QR-Code Generator เป็นต้น 
___

####  1.1 ชื่อเซอร์วิส : Push Notification Services
 **คำอธิบาย** : เซอร์วิสสำหรับการแจ้งเตือนไปยัง IntaniaBuddy Mobile Application แจ้งเตือนแบบ Remote Push 
___
####  1.1.1 ชื่อ API : ConfirmSend
 **คำอธิบาย** : ตรวจสอบจำนวนกลุ่มเป้าหมายและจำนวนอุปกรณ์ที่สามารถจะส่งไปได้
``
Authorization : Bearer Token
``

#### Headers: "Content-Type=application/json"

URL : [https://apis.eng.psu.ac.th/asset/notification/v1/confirmsend](https://apis.eng.psu.ac.th/asset/notification/v1/confirmsend)
***
## Method: POST
 **Input Parameters : Request in body data JSON format**

```
    {
         "headings" : "ชื่อหัวข้อเรื่องการส่ง", ชนิดของข้อมูล string 
         "contents" : "เนื้อหาอธิบายรายละเอียดของหัวข้อเรื่อง", ชนิดของข้อมูล string  
         "url" "https://www.eng.psu.ac.th", link url ที่เกี่ยวข้องกับข้อความ เมื่อได้รับเปิดอ่านข้อความ ใส่่ค่าว่างได้หากไม่มี link ชนิดของข้อมูล string  
         "std_code" :[] ชนิดของข้อมูล Array รหัสนักศึกษา 13 หลัก ใส่ค่า null หากไม่กำหนด
         "dept_id"  :[] ชนิดของข้อมูล Array รหัสนักศึกษา 13 หลัก ใส่ค่า null หากไม่กำหนด
        "major_id":[], ชนิดของข้อมูล Array รหัสสาขาวิชา ใส่ค่า null หากไม่กำหนด
        "year_status":[], ชนิดของข้อมูล Array ชั้นปีที่เรียน เช่น 1 หมายถึงปีที่ 1 ใส่ค่า null หากไม่กำหนด
        "sub_id":"", ชนิดของข้อมูล string รหัสวิชา เช่น 200-201 กำหนดได้เพียง 1 วิชา
        "section":[] ชนิดของข้อมูล Array ตอนของการลงทะเบียน เช่น 01 หมายถึง ตอน 01
    }
```
***
# Respone data:
```
    {
        "total_forced_recipients":1214, ชนิดของข้อมูล Integer จำนวนของกลุ่มเป้าหมายตามที่ระบุมาจาก data input
         "total_messageable_recipients": 738, ชนิดของข้อมูล Integer จำนวนของอุปกรณ์ที่สามารถส่งไปยังผู้รับได้
        "recipients":[] ชนิดของข้อมูล Array รายการผู้รับและข้อมูลอุปกรณ์ที่สามารถส่งได้
    }
```
***
# ERROR

**Response Status: 401 Unauthorized // Access Token หมดอายุ**
```
    {
        "error": "invalid_token",
        "error_description": "The access token provided is invalid"
    }
```
***
# 1.2 Email Service
***
# 1.3 PDF Service
***


