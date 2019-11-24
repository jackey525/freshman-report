# OpenCC

### PHP 簡繁體轉換

#### install OpenCC
     git clone https://github.com/BYVoid/OpenCC.git
     cd OpenCC
     make
     sudo make install
     
#### install opencc4php
     git clone [email protected]:NauxLiu/opencc4php.git
     cd opencc4php
     phpize
     ./configure
     make && sudo make install
     
#### mods-available目錄下建立一個 opencc.ini的檔案
     cd /etc/php/7.2/mods-available/
     sudo vi opencc.ini
     內容
          ; configuration for php opencc module
          ; priority=20
          extension=opencc.so
     sudo phpenmod opencc
     sudo systemctl reload apache2
     
#### test

     $od = opencc_open("s2twp.json"); //傳入配置檔名
     $text = opencc_convert("简体", $od);
     echo $text;
     opencc_close($od);
     
     //輸出  簡體
