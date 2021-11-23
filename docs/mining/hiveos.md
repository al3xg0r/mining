## Документация по майнеру 💎toncoin для HiveOS

Пользовательскую сборку майнера HiveOS нужно скачать по ссылке с официального репозитория на [GitHub](https://github.com/tontechio/pow-miner-gpu-hiveos/releases "GitHub")

> Это ранняя версия майнера для HiveOS, поэтому не стесняйтесь [сообщать](https://github.com/tontechio/pow-miner-gpu-hiveos/issues "сообщать") о проблемах.

##### Ограничения

- Автообновление HiveOS не поддерживается
- ~~Подробная статистика HiveOS не поддерживается~~ Поддерживается для CUDA

### Настройка HiveOS

> Основано на официальном руководстве по HiveOS. В случае непонимания, затруднений и т.д., пожалуйста, обращайтесь к [оригинальным руководствам](https://hiveos.farm/getting_started-quick_install/ "оригинальным руководствам")

- Пропустите этот шаг, если ваша учетная запись и установка HiveOS уже настроены
- [Загрузите](https://download.hiveos.farm/latest/ "Загрузите") файл `hiveos*.img.gz`
- Подготовьте внешний накопитель (минимум 8 Гб), который будет использоваться для записи файла `hiveos*.img.gz` - USB-накопитель, внешний SSD или другой тип внешнего накопителя
- Рекомендации HiveOS: 
> [Etcher](https://www.balena.io/etcher/ "Etcher") - это рекомендуемый инструмент для записи образов Hive на диски. Он поддерживает Windows, Mac, Linux. Он также может записывать распакованные ZIP-архивы.
В качестве альтернативы вы можете использовать [Rufus](https://rufus.akeo.ie/ "Rufus") как инструмент записи образов.
...
Продвинутые пользователи Unix (Linux или Mac) могут использовать dd для записи RAW-образа на диск. Что-то вроде `dd if=hiveos-XXX.img of=/dev/sdX bs=10M status=progress`. Но будьте осторожны с поиском выходного диска "of", используйте `fdisk -l` для списка разделов.
...
[Прочитать полностью](https://hiveos.farm/install/ "Прочитать полностью") 

- Записать `hiveos*.img.gz` на выбранный внешний диск в двоичном режиме
- [Создайте учетную запись HiveOS](https://hiveos.farm/ "Создайте учетную запись HiveOS")
- Запомните `RigID` и `RigPassword`
- Установите на ПК/сервер/ноутбук для майнинга с помощью внешнего диска с прошивкой. Ваш ПК/сервер/ноутбук должен иметь подключение к Интернету
- После загрузки используйте свой `RigID` и `RigPassword` для продолжения работы
- Откройте веб-конфигурацию вашей HiveOS

### Настройка майнера

- Создайте "кошелек TON" в учетной записи HiveOS с пользовательской монетой "toncoin"
- Источник для монеты необязателен, поэтому вы можете найти его или проверить [оригинальную документацию](https://hiveos.farm/guides-how_to_start_mine_in_Hive_OS/ "оригинальную документацию")
- Заполните и **дважды** проверьте адрес вашего личного кошелька в поле Адрес
- Теперь вы должны настроить HiveOS для связи с  майнером. Пример ниже:

| OPTION  | VALUE  | COMMENT  |
| ------------ | ------------ | ------------ |
| Coin  | toncoin  |   |
|  Wallet | {АДРЕС ВАШЕГО КОШЕЛЬКА TONCOIN}  |   |
|  Pool | Configure in miner  |   |
|  Name |  TON flight sheet |   |
|  Miner Name | `tonminer_cuda_hiveos_x86_64` или `tonminer_opencl_hiveos_x86_64`  | Генерируется автоматически на основе URL-адреса установки майнера, приведенного ниже  |
| Miner Installation URL  |  `https://github.com/tontechio/pow-miner-gpu-hiveos/releases/latest/download/tonminer_cuda_hiveos_x86_64.tar.gz` или `https://github.com/tontechio/pow-miner-gpu-hiveos/releases/latest/download/tonminer_opencl_hiveos_x86_64.tar.gz` |  Зависит от вашей видеокарты. Выберите версию cuda для Nvidia или версию opencl для AMD |
|Miner Hash algorithm   |   | Нет значения (пусто)  |
| Miner Wallet and worker template  |`%WAL%`   |  Только номер кошелька для упрощения механики сценария |
| Miner Pool URL  | `stratum+tcp://p2p.antpool.com:3333`  |   Оставьте значение по умолчанию, это значение не используется майнером|
| Miner Extra config arguments  |   | см. ниже  |

> Miner Extra config arguments
```
"miner_0": ["kf-P_TOdwcCh0AXHhBpICDMxStxHenWdLCDLNH5QcNpwMHJ8",0,32,0,2],
"miner_1": ["kf-P_TOdwcCh0AXHhBpICDMxStxHenWdLCDLNH5QcNpwMHJ8",1,32,0,2],
"miner_2": ["kf-P_TOdwcCh0AXHhBpICDMxStxHenWdLCDLNH5QcNpwMHJ8",2,32,0,2],
"miner_3": ["kf-P_TOdwcCh0AXHhBpICDMxStxHenWdLCDLNH5QcNpwMHJ8",3,32,0,2],
"tmpfs_logs_enable": "yes"
```

- Применить изменения в опциях майнера
- Вот и все

### Примечания

- Загрузите последнюю версию майнера: 
    - [CUDA](https://github.com/tontechio/pow-miner-gpu-hiveos/releases/latest/download/tonminer_cuda_hiveos_x86_64.tar.gz "CUDA")
    - [OpenCL](https://github.com/tontechio/pow-miner-gpu-hiveos/releases/latest/download/tonminer_opencl_hiveos_x86_64.tar.gz "OpenCL")
- Скопируйте загруженный архив в системный каталог `/hive/miners/custom/downloads/`
- Откройте терминал HiveOS (консоль) и выполните команды: 
    - `cd /hive/miners/custom/downloads/`
    - `tar -xf tonminer_*_hiveos_x86_64.tar.gz -C ../`
- Запустите майнер

### Обновление инструментов майнера и конфигурации блокчейна

В настоящее время майнер TON не поддерживает систему обновления майнеров HiveOS. Для обновления до последней версии майнера просто следуйте инструкциям по ручной установке.
