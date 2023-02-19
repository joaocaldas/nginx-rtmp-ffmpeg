# nginx-rtmp-ffmpeg

No arquivo ```nginx.conf```, o ffmpeg ouve transmissão em ```http://172.16.100.12:8000``` e converte para 3 bitrates diferentes utilizando o parâmetro do hls ```hls_variant```.

A transmissão foi feita pelo Radio Boss, mas pode ser utilizado qualquer serviço de streaming. Neste caso, está subindo em 320kbps utilizando OPUS.

Lembrando que o HLS só suporta AAC, ou seja, independente da entrada, a saída sempre vai ser em AAC.

Para utilizar o rtmp no nginx, é necessário o módulo para NGINX ```libnginx-mod-rtmp``` https://packages.debian.org/sid/libnginx-mod-rtmp

Para instalar no Debian 11:
```sudo apt install libnginx-mod-rtmp```


** RECOMENDAÇÃO ** 
Compile seu ffmpeg com libfdk_aac, a qualidade melhora consideravelmente. Você pode utilizar um bitrate menor (menos tráfego) com uma qualidade superior ao AAC compilado nativamente do ffmpeg.
