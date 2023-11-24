# API RESPON LOGIC TOURIFY

## Login/Register Area doPost(e)
### Check Email Address 
```json
{
  "error": false,
  "message": "Email already exists",
  "codeVerif": 123456
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan email sudah terdaftar (nilai yang di Post adalah e.email)
```json
{
  "error": true,
  "message": "Email added successfully",
  "codeVerif": 123456
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan email belum terdaftar (nilai yang di Post adalah e.email)

### Check Password
```json
{
  "error": false,
  "message": "Login successful"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan kata sandi benar atau sesuai (nilai yang di Post adalah e.email, e.password)
```json
{
  "error": true,
  "message": "Login failed"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan kata sandi salah atau tidak sesuai (nilai yang di Post adalah e.email, e.password)

### Check Verification Code
```json
{
  "error": false,
  "message": "Success"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan code verifikasi benar atau sesuai (nilai yang di Post adalah e.email, e.codeVerif)
```json
{
  "error": true,
  "message": "Failed"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan code verifikasi salah atau tidak sesuai

### Create Password
```json
{
  "error": false,
  "message": "Login successful"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan membuat password baru, login dan kata sandi benar atau sesuai (nilai yang di Post adalah e.email, e.password)
```json
{
  "error": true,
  "message": "Error in the system",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan login dan system mengalami error

### Reset Password
```json
{
  "error": false,
  "message": "Success",
  "codeVerif": 123456
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan reset password (nilai yang di Post adalah e.email)
```json
{
  "error": true,
  "message": "Error in the system",
  "codeVerif": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan reset password dan system mengalami error


## Home Area doGet(e)
### get Daftar Wisata
```json
{
  "error": false,
  "message": "Success",
  "data": [
    {
      "id": 1,
      "nama": "",
      "type": "",
      "regency": "",
      "province": "",
      "country": "",
      "rating": "",
      "totalReview": "",
      "totalCulinary": "",
      "openOn": "",
      "closedOn": "",
      "ticketPrice": 7000,
      "caption": "",
      "photo": "",
      "lat": "",
      "lon": "",
      "tourGuide": [
        {
          "id": 1,
          "nama": "Sarah",
          "email": "sarah@example.com",
          "servicePrice": 9000,
          "photoProfile": "",
          "totalReview": ""
        },
        {
          "id": 2,
          "nama": "Ratih",
          "email": "ratih@example.com",
          "servicePrice": 7000,
          "photoProfile": "",
          "totalReview": ""
        }
      ]
    },
    {
      "id": 2,
      "nama": "",
      "type": "",
      "regency": "",
      "province": "",
      "country": "",
      "rating": "",
      "totalReview": "",
      "totalCulinary": "",
      "openOn": "",
      "closedOn": "",
      "ticketPrice": 8000,
      "caption": "",
      "photo": "",
      "lat": "",
      "lon": "",
      "tourGuide": [
        {
          "id": 1,
          "nama": "Sarah",
          "email": "sarah@example.com",
          "servicePrice": 9000,
          "photoProfile": "",
          "totalReview": ""
        },
        {
          "id": 2,
          "nama": "Ratih",
          "email": "ratih@example.com",
          "servicePrice": 7000,
          "photoProfile": "",
          "totalReview": ""
        }
      ]
    }
  ]
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika berhasil melakukan get daftar wisata 
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika gagal melakukan get daftar wisata atau system mengalami error


## Detail Area doPost(e)
### Booking Perjalanan (dengan Tourguide)
```json
{
  "error": false,
  "message": "Trip Booked",
  "data": {
    "id": 1,
    "code": "myTRF19112023120105",
    "total": 29000,
    "withTourGuide": true,
    "statusPayment": 0
  }
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan booking perjalanan dan berhasil (statusPayment, 0 = pending, 1 = success, 2 = failed). (nilai yang di Post adalah e.usersId, e.name, e.email, e.tripDate, e.wisataId, e.tourGuideId, e.telepon, e.note)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user gagal melakukan booking perjalanan atau system mengalami error

### Booking Perjalanan (tanpa Tourguide)
```json
{
  "error": false,
  "message": "Trip Booked",
  "data": {
    "id": 1,
    "code": "myTRF19112023120105",
    "total": 29000,
    "withTourGuide": false,
    "statusPayment": 0
  }
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan booking perjalanan dan berhasil (statusPayment, 0 = pending, 1 = success, 2 = failed). (nilai yang di Post adalah e.usersId, e.name, e.email, e.tripDate, e.wisataId, e.telepon)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user gagal melakukan booking perjalanan atau system mengalami error

### Add Wisata Favorit
```json
{
  "error": false,
  "message": "Successfully added to favorites"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan add favorite dan berhasil. (nilai yang di Post adalah e.usersId, e.email, e.wisataId)
```json
{
  "error": true,
  "message": "Failed to add to favorites"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika user melakukan add favorite dan gagal


## Pembayaran Area doPost(e)
### Status Pesanan
```json
{
  "error": false,
  "message": "Success",
  "data": {
    "id": 1,
    "code": "myTRF19112023120105",
    "total": 29000,
    "withTourGuide": false,
    "statusPayment": 0
  }
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika post status pesanan dan berhasil (statusPayment, 0 = pending, 1 = success, 2 = failed). (nilai yang di Post adalah e.usersId, e.email, e.bookingId, e.bookingCode)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika post status pesanan atau system mengalami error. (nilai yang di Post adalah e.usersId, e.email, e.bookingId, e.bookingCode)


## Kuliner Area doGet(e)
### get Daftar Kuliner
```json
{
  "error": false,
  "message": "Success",
  "data": [
    {
      "id": 1,
      "name": "",
      "type": "",
      "regency": "",
      "province": "",
      "country": "",
      "caption": "",
      "photo": ""
    },
    {
      "id": 2,
      "name": "",
      "type": "",
      "regency": "",
      "province": "",
      "country": "",
      "caption": "",
      "photo": ""
    }
  ]
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika berhasil melakukan get daftar kuliner (nilai parameter yang di get adalah e.province)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika gagal melakukan get daftar kuliner atau system mengalami error


## My Favorit Wisata Area doPost(e)
### My Favorit Wisata
```json
{
  "error": false,
  "message": "Success",
  "wisataId": "1,78,90,81"
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika berhasil melakukan post my favorit wisata (nilai yang di post adalah e.usersId, e.email)
```json
{
  "error": true,
  "message": "Error in the system",
  "wisataId": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika gagal melakukan post my favorit wisata atau system mengalami error


## My Tickets Area doPost(e)
### My Tickets
```json
{
  "error": false,
  "message": "Success",
  "data": [
    {
      "id": 1,
      "wisataId: 1,
      "codeBooking: "myTRF19112023140220",
      "statusCheckIn": 0,
      "dateBooking": "",
      "dateTrip": "",
      "withTourGuide": true,
      "tourGuideId": 1,
      "statusPayment": 1,
      "totalTicket": 1,
      "ticketPrice": 25000,
      "totalServicesTourguide": 100000,
      "totalDiscount": 5000,
      "applicationFee": 3000,
      "totalPrice": 123000,
      "notes": "jangan buat saya menunggu lama ya mas"
    },
    {
      "id": 2,
      "wisataId: 2,
      "codeBooking: "myTRF19112023151210",
      "statusCheckIn": 1,
      "dateBooking": "",
      "dateTrip": "",
      "statusCheckIn": 0,
      "withTourGuide": false,
      "tourGuideId": 0,
      "statusPayment": 1,
      "totalTicket": 1,
      "ticketPrice": 25000,
      "totalServicesTourguide": 0,
      "totalDiscount": 5000,
      "applicationFee": 3000,
      "totalPrice": 23000,
      "notes": null
    }
  ]
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post my tickets dan berhasil (nilai yang di post adalah e.usersId, e.email)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post my tickets dan gagal atau system mengalami error 


## My Profile Area  doGet(e)
### My Profile
```json
{
  "error": false,
  "message": "Success",
  "profileUser": {
      "usersId": 1,
      "name": "Zain",
      "email": "zain@example.com",
      "username": "zainalabidin1453",
      "dateBirth": "",
      "gender": 1,
      "address": "",
      "village": "",
      "subdistric": "",
      "regency": "",
      "province": "",
      "country": "",
      "zipCode": "",
      "citizenship": "",
      "noTelepon": "",
      "noWhatsapp": "",
      "statusAccount": 0,
      "isVerification": false
  }
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan get my profile dan berhasil (nilai yang di post adalah e.usersId, e.email)
```json
{
  "error": true,
  "message": "Error in the system",
  "profileUser": null,
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan get my profile dan gagal atau system mengalami error


## My Profile Area doPost(e)
### Edit Profile
```json
{
  "error": false,
  "message": "Profile edited successfully",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post edit profile dan berhasil (nilai yang di post adalah e.usersId, e.name, e.username, e.email, e.dateBirth, e.gender, e.address, e.village, e.subdistric, e.regency, e.province, e.country, e.zipCode, e.citizenship, e.noTelepon, e.noWhatsapp)
```json
{
  "error": true,
  "message": "Profile failed to edit",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post edit profile dan gagal

### Change Password
```json
{
  "error": false,
  "message": "Password changed successfully",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post ubah password dan berhasil (nilai yang di post adalah e.usersId, e.email, e.password)
```json
{
  "error": true,
  "message": "Password failed to change",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post ubah password dan gagal

### Change payment
```json
{
  "error": false,
  "message": "Payment added successfully",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post add pembayaran dan berhasil (nilai yang di post adalah e.usersId, e.email, e.noRekening, e.nameBank, e.kcp, e.nameEwallet, e.noEwallet)
```json
{
  "error": true,
  "message": "Payment failed to add",
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika melakukan post add pembayaran dan gagal


## Scan Objek Area  doPost(e)
### Scan Objek
```json
{
  "error": false,
  "message": "Success",
  "data": {
    "name" : "",
    "type" : "",
    "description" : "",
    "photo" : ""
  }
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika berhasil melakukan post foto objek dan data ditemukan  (nilai yang di post adalah e.photoObject)
```json
{
  "error": false,
  "message": "Success",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika berhasil melakukan post foto objek dan data tidak ditemukan  (nilai yang di post adalah e.photoObject)
```json
{
  "error": true,
  "message": "Error in the system",
  "data": null
}
```
**Catatan:** Respon JSON diatas adalah hasil respon ketika gagal melakukan post foto objek atau system mengalami error
