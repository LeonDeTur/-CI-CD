# CI/CD. Семинар 04. Troubleshooting (диагностика и решение проблем в CI/CD)

## Задача
Сделать отдельный шаблон CI и отдельный репозиторий с шаблонами, подключить их к своему основному репозиторию через include




## Решение
Создан локальный файл `local-smoke-tests.gitlab-ci.yml`

```yaml
smoke-test-job:
  script: echo "SMOKE"
```

Создан основной файл `.gitlab-ci.yml`

```yaml
include:
  - local: local-smoke-tests.gitlab-ci.yml
#  - remote: https://github.com/LeonDeTur/-CI-CD/blob/main/remote_included-file.yml
# Ни cобственные файлы в репо, ни ссылка на гитхаб не сработали
# Поэтому взял отсюда:
  - remote: https://gitlab.com/ci-cd7655047/5/-/raw/main/remote-included-file.yml
```

Файл с таким же содержанием, есть в этом репозитории: `remote_included-file.yml`



Repository Seminar04
![repository](https://github.com/LeonDeTur/-CI-CD/blob/main/1.png)

Remote included file job
![remote included file job](https://github.com/LeonDeTur/-CI-CD/blob/main/2.png)

Pipeline passed
![pipeline passed](https://github.com/LeonDeTur/-CI-CD/blob/main/3.png)

