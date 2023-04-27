# Setup AWS EC2 with docker
Login to AWS console
Lauch instances
In Amazon Machine Image (AMI)
search image  for Docker on Ubuntu..
I suggest  using amzn2-ami-ecs-hvm-2.0

### sau khi tạo xong instance EC2
tạo security group, 
add inbound rule ssh from 0.0.0.0/0
add port khác tùy vào port server sẽ chạy


tải file pem về => file xxx.cer
copy vào ~/.ssh
dùng lệnh ssh -i xxx.cer <username>@<instanceEC2Ip> để truy cập vào instance thông qua ssh

### thêm public key để ssh từ máy khác
tạo key pair tải về
dùnh lệnh ssh-keygen -y -f <filename>.cer để lấy đc public key trên máy tính mới
copy public key vào .ssh/authorized_keys trên EC2 từ máy giữ file xxx.cer

chạy lệnh ssh-add <filename>.cer
thì sau này chỉ cần ssh <username>@<instanceEC2Ip>
