# Nvidia

##### Настройки майнинга для карт Nvidia

1. Установить актуальные драйвера с поддержкой CUDA по этой [ссылке](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html "ссылке").

2. Скачиваем архив [minertools-cuda-windows-x86-64.zip](https://github.com/tontechio/pow-miner-gpu/releases "minertools-cuda-windows-x86-64.zip")

3. Распаковываем архив и добавляем к его содержимому файл с текущей конфигурацией сети [global.config.json](https://newton-blockchain.github.io/global.config.json "global.config.json").

4. Затем необходимо скачать **run_config.ini** и **run_cuda.bat**, для этого переходим по этой [ссылке](https://github.com/tontechio/pow-miner-win-util "ссылке") и скачиваем ZIP архив, как показано на скриншоте. После этого забираем из архива два вышеуказанных файла и добавляем их в общую папку.
 ![](https://raw.githubusercontent.com/tonminingdocs/tonmd.github.io/main/docs/media/config.png "config")

5. Открываем **run_config.ini** 
```
GIVER_ADDR=giver_address
MY_ADDR=my_address
GPU_ID=0
GPU_PLATFORM_ID=0
BOOST_FACTOR=64
CONFIG_FILE=global.config.json
USE_LOG=N
LOG_FILE=gpu_0_miner_log.txt
TEST_TIME=10
```
и заменяем в первой строке **giver_address** на одного из [10 Giverов](https://ton.org/mining "10 Giver`ов")
