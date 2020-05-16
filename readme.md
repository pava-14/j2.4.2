# Задача № 2 "@CsvFileSource"

## Краткое описание

1. В проект с лекции дописаны непроверенные сценарии. 
2. Реализовано чтение данных из файла формата CSV. 

## Код автотестов

```java
    @ParameterizedTest
    @CsvFileSource(resources = "/data.csv")
    void shouldCalculate(String test, long amount, boolean registered, long expected) {
        BonusService service = new BonusService();

        // вызываем целевой метод:
        long actual = service.calculate(amount, registered);

        // производим проверку (сравниваем ожидаемый и фактический):
        assertEquals(expected, actual);
    }
```
## Файл 
    data.csv:
```
registered user and bonus under limit,100060,true,30
registered user and bonus over limit,100000060,true,500
unregistered user and bonus under limit,100060,false,10
unregistered user and bonus over limit,100000060,false,500
```
## Лог
```
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running ru.netology.bonus.BonusServiceTest
[INFO] Tests run: 4, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.117 s - in ru.netology.bonus.BonusServiceTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 4, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  4.154 s
[INFO] Finished at: 2020-05-16T19:00:34+07:00
[INFO] ------------------------------------------------------------------------
```