# Домашняя работа №4 курса Otus Linux.Professional  
## ZFS

- script.sh
    - Создает зеркальный том на /dev/sd{b,c};
    - Создает несколько разделов с разным уровнем компресии (gzip,gzip-9,zle,lzjb,lz4), заполняет их файлами для последующего определения уровня сжатия содержимого;
    ```shell
    #Вывод команды из которой видно какой из алгоритмов лучше
    [root@server ~]# zfs get compression,compressratio
    NAME                     PROPERTY       VALUE     SOURCE
    pool_R1                  compression    off       default
    pool_R1                  compressratio  2.22x     -
    pool_R1/compress_gzip    compression    gzip      local
    pool_R1/compress_gzip    compressratio  3.60x     -
    pool_R1/compress_gzip-9  compression    gzip-9    local
    pool_R1/compress_gzip-9  compressratio  3.69x     -
    pool_R1/compress_lz4     compression    lz4       local
    pool_R1/compress_lz4     compressratio  2.35x     -
    pool_R1/compress_lzjb    compression    lzjb      local
    pool_R1/compress_lzjb    compressratio  2.08x     -
    pool_R1/compress_zle     compression    zle       local
    pool_R1/compress_zle     compressratio  1.27x     -
    ```
    - Импортирует зеркальный том, полученый от преподавателя
    - Отображает информацию о свойствах томов и разделов zfs: type, available, recordsize, checksum, compression, compressratio  
    - Импортирует снапшот с секретным сообщением
    - находит и показывает секретное сообщение

