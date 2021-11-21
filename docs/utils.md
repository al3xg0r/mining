## Утилиты для работы с майнером (Windows)
Скачать утилиты нужно из официального репозитория [GitHub ](https://github.com/tontechio/pow-miner-win-util "GitHub ")

#### Файлы

- `run_config.ini` - конфигурация майнера и инструментов

- `test_cuda.bat` - запуск теста производительности для [Nvidia](/windows/nvidia "Nvidia GPU")

- `run_cuda.bat` - запуск майнера для [Nvidia](/windows/nvidia "Nvidia GPU")

- `test_opencl.bat` - запуск теста производительности для [AMD](/windows/amd "AMD GPU")

- `run_opencl.bat` - запуск майнера для [AMD](/windows/amd "AMD GPU")

#### Использование

1. Скачайте, распакуйте и поместите в ту же директорию, где находятся файлы `*.exe` майнера
2. Отредактируйте **run_config.ini**
3. Запустите **test_cuda.bat** или **test_opencl.bat** (в зависимости от вашей видиокарты) для проверки производительности и оптимального значения [BOOST_FACTOR](/bf/ "BOOST_FACTOR")
4. Не забудьте включить (**USE_LOG=Y**) или отключить (**USE_LOG=N**) логирование майнера
5. Запустите **run_cuda.bat** (для Nvidia) или **run_opencl.bat** (для AMD) для запуска майнера

#### run_config.ini

`GIVER_ADDR`: `auto` / `random` название стратегии или адрес постоянного гивера, выберите одно из [Givers](https://ton.org/mining "Givers")

`MY_ADDR`: адрес вашего личного [кошелька](https://ton.app/wallets/ "кошелька")

`GPU_ID`: ваша видеокарта. Для первой ставим `GPU_ID=0`, для второй `GPU_ID=1` и т.д.

`GPU_PLATFORM_ID`: только для OpenCL (AMD). Проверьте статистику драйверов и/или запустите майнер - она покажет номер платформы и идентификатор видеокарт(ы).

`BOOST_FACTOR`:  настройка производительности видеокарты. Запустите **test_cuda.bat** (для Nvidia) или **test_opencl.bat** (для AMD) для получения оптимального значения.

`CONFIG_FILE`: скачать [global.config.json](https://newton-blockchain.github.io/global.config.json "global.config.json") и сохранить в дерикторию с майнером

`USE_LOG`: значение `Y`включить логирование. Значение `N` - отключить

`LOG_FILE`: имя файла, используемое при `USE_LOG=Y`

`TEST_TIME`: время в секундах для каждого теста в **test_cuda.bat** (для Nvidia) или **test_opencl.bat** (для AMD) для получения значения [BOOST_FACTOR](/bf/ "BOOST_FACTOR"). Меньше - для получения более быстрых результатов, больше - для получения более точных результатов.