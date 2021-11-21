# Nvidia

##### Настройки майнинга для карт Nvidia

1. Установить актуальные драйвера с поддержкой CUDA по этой [ссылке](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html "ссылке").

2. Скачиваем архив [minertools-cuda-windows-x86-64.zip](https://github.com/tontechio/pow-miner-gpu/releases "minertools-cuda-windows-x86-64.zip")

3. Распаковываем архив и добавляем к его содержимому файл с текущей конфигурацией сети [global.config.json](https://newton-blockchain.github.io/global.config.json "global.config.json").

4. Затем необходимо скачать **run_config.ini** и **run_cuda.bat**, для этого переходим по этой [ссылке](https://github.com/tontechio/pow-miner-win-util "ссылке") и скачиваем ZIP архив, как показано на скриншоте. После этого забираем из архива два вышеуказанных файла и добавляем их в общую папку.
 ![](https://raw.githubusercontent.com/tonminingdocs/tonmd.github.io/main/docs/media/config.png "config")

5. Открываем Открываем [run_config.ini](/utils?id=run_configini) 
```
GIVER_ADDR=giver_address или auto/random
MY_ADDR=my_address
GPU_ID=0
GPU_PLATFORM_ID=0
BOOST_FACTOR=64
CONFIG_FILE=global.config.json
USE_LOG=N
LOG_FILE=gpu_0_miner_log.txt
TEST_TIME=10
```
и заменяем в первой строке **giver_address** на одного из [10 Giverов](https://ton.org/mining "10 Giver`ов") или ставим одну из стратегий auto/random

> **auto** - выбирается автоматически гивер с наиболее легкими задачами, **random** - выбирается случайный гивер

6. Вместо **my_address** впишите адрес своего кошелька, в результате документ должен принять следующий вид:
```
GIVER_ADDR=Ef8JfFUEJhhpRW80_jqD7zzQteH6EBHOzxiOhygRhBdt44YH
MY_ADDR=EQDCH6vT0mVvp0bBYNjoONpkgb51NMPNOJXFQWG54XoIAs5Y
GPU_ID=0
GPU_PLATFORM_ID=0
BOOST_FACTOR=64
CONFIG_FILE=global.config.json
USE_LOG=N
LOG_FILE=gpu_0_miner_log.txt
TEST_TIME=10
```
7. Убедитесь, что **все** указанные файлы находятся в одной папке, как на скриншоте ниже.
![](https://raw.githubusercontent.com/tonminingdocs/tonmd.github.io/main/docs/media/mine-folder.png)

8. Далее нужно запустить файл **run_cuda.bat** (в простонароде - батник), если всё было сделано верно, вы увидите окно, как на скриншоте ниже.
![](https://raw.githubusercontent.com/tonminingdocs/tonmd.github.io/main/docs/media/runsync.png)
9. После завершения синхронизации начнётся майнинг, найденные монеты будут начисляться на адрес указанный в 6 шаге. **PROFIT!!!**