# Отключение рекламы на Яндекс Станции Макс

Статья: https://dzen.ru/a/aFMHiIKVCkldIkdU

Утилита tls_proxy описана в статье [https://dzen.ru/a/aE2nH724O0UJBTL_](https://dzen.ru/a/aE2nH724O0UJBTL_), исходные тексты: https://github.com/mamaich/yahome-no-ads (брать оттуда только утилиту, скрипты для Max свои).

Файлы для Max:  
myinit-max.c - замена /init в system (чтобы он запустился - добавить init=/myinit-max в командную строку ядра)  
mysudo.c - простой аналог sudo, через сокет /dev/myinit-socket взаимодействиует с myinit чтобы запустить команду или sh с правами root  
  
Компиляция:  
.../musl-arm/bin/musl-gcc -static -s ./myinit-max.c  -o myinit-max  
.../musl-arm/bin/musl-gcc -static -DDEBUG -s ./myinit-max.c  -o myinit-max-dbg  
