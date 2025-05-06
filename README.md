# lsb_aes_tool
rebuild -b lsb_aes_tool
checkwork:
1.tạo file chứa thông tin cần giấu(sudo nano secret.txt)

2.mã hóa aes(openssl enc -aes-256-cbc -salt -in secret.txt -out secret.enc -pass pass:yourpassword)

cài công cụ steghide mã hóa lsb(sudo apt install steghide)

4.giấu tin đã mã hóa vào ảnh(steghide embed -cf cover.jpg -ef secret.enc)

5.trích xuất mã hóa từ ảnh(steghide extract -sf cover.jpg)

6.giải mã(openssl enc -d -aes-256-cbc -in secret.enc -out secret_decrypted.txt -pass pass:yourpassword)
