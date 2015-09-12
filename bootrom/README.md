Black Swift bootrom images
--------------------------

This directory contains pre-built bootrom images for Black Swift board.

You can build your own bootrom images from sources.
Please see build instructions in this Black Swift Russian wiki article:
[Сборка прошивки из исходников](http://www.black-swift.ru/wiki/index.php?title=%D0%A1%D0%B1%D0%BE%D1%80%D0%BA%D0%B0_%D0%BF%D1%80%D0%BE%D1%88%D0%B8%D0%B2%D0%BA%D0%B8_%D0%B8%D0%B7_%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D0%BD%D0%B8%D0%BA%D0%BE%D0%B2).


black-swift.20150401.bin
------------------------

The file black-swift.20150401.bin contains **original** Black Swift bootrom image.


MAC address
-----------

Black Swift typical MAC addresses are 80-7B-85-9x-xx-xx
(see http://www.black-swift.ru/forum/welcome-mat/94-informatsiya-o-pervom-tirazhe-plat-dlya-rossii for details).

The MAC address is stored in the bootrom image file at offset 0xff0000.

To change MAC address to e.g. 80-7B-85-94-32-10
in the file black-swift.20150401.bin use this command:

    $ echo -n -e "\x80\x7B\x85\x94\x32\x10" | dd of=black-swift.20150401.bin bs=1K seek=16320 conv=notrunc 2>/dev/null
