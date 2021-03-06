# Boost Factor

> Бустфактор (Boost Factor) - это тюнинг чтобы довыжать из выжатого, максимально оптимизировать работу карты под майнера и числа строго индивидуальны даже в рамках одной модели и одной системы

### Оптимальный Boost Factor

Чтобы определить оптимальный коэффициент форсирования, запустите бенчмарк со следующими параметрами. Поочередно будут запущены короткие майнинги с разными коэффициентами усиления. В конце будет показано наилучшее значение параметра, при котором был получен максимальный хэшрейт за указанный период.

> Тест нужен для определения оптимального параметра Boost Factor, благодаря которому можно добиться максимальной скорости работы для видеокарты.

### Запуск теста Boost Factor

Нужно запустить файл **test_cuda.bat** для **NVidia**, **test_opencl.bat** для **AMD** ([скачаные от сюда](https://github.com/tontechio/pow-miner-win-util "скачаные от сюда")). Запустится тестирование, которое продлится несколько минут, по истечению которого будет примерно такой результат:

![](https://raw.githubusercontent.com/tonminingdocs/tonmd.github.io/main/docs/media/bf-test.png)

Полученное в тесте число (best boost factor) в данном случае 1 записываем в конфиг [run_config.ini](/utils?id=run_configini) `(BOOST_FACTOR=1)`:

```
GIVER_ADDR=giver_address
MY_ADDR=my_address
GPU_ID=0
GPU_PLATFORM_ID=0
BOOST_FACTOR=1
CONFIG_FILE=global.config.json
USE_LOG=N
LOG_FILE=gpu_0_miner_log.txt
TEST_TIME=10
```