You can copy the following code and create a new text file and change it's extension to .bat and then paste the code inside!

```
@echo on
cls

set _date=%DATE%-%TIME%
set _date=%_date:/=-%
set _date=%_date: =-%
set _date=%_date::=-%
set _date=%_date:.=-%

::REGISTRY/PROJECT/REPOSITORY:TAG
set REGISTRY=
set PROJECT=
set REPOSITORY=
set TAG=%_date%

::Credentials
set ACCOUNT=
set TOKEN=

docker build -f ./Dockerfile -t %REGISTRY%/%PROJECT%/%REPOSITORY%:%TAG% ."
docker login -u %ACCOUNT% %REGISTRY% -p %TOKEN%
docker push %REGISTRY%/%PROJECT%/%REPOSITORY%:%TAG%
docker logout %REGISTRY%

pause
```
