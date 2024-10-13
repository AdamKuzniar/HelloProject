# Odpalanie Obrazu
Obraz na podstawie docker File, budujemy obraz:
"docker build -t hello-backend" 
-t flaga do nazwania obrazu


docker run -it hello-backend sh
 sh - odpalenie połączenia shell
docker run -it --rm -v /mnt/c/Users/adamk/Desktop/Dev:/home/dev hello-backend sh
 it - interactive
 rm - usuń kontener
 v  - montowanie wolumentu 
 sh - połączenie shell