# Шпаргалка по Git

## Cоздание локального репозитория

Создав папку любым способом  необходимо **проинициализировать** репозиторий:
воспользовавшись командой:

```bash
git init

git add
git commit -m ""
git push
``` 

Пример _курсива_ и **жирного** текста.

## Работа с  GitHub

1. Необходимо пройти регистрацию на **GitHub**
2. Создать удаленный репозиторий. Для этого:
- Заходим в __Repositories__
- жмем кнопку **New**
- задаем имя репозиотрию
- выбираем __публичный__ или __приватный__ режим
- нажимаем **Create**
3. В новом окне мы видим множество способов связать локальный репозирий с удаленным. Мы воспользуемся привязкой по ssh

## Работа с SSH ключами

Нам необходимо создать пару ключей ssh(**SSH** - **S**ecure **Sh**ell Protocol) - сетевой протокол обмена данными. Он обеспечивает безопасный обмен данными в сети

SSH состоит из **приватного** (личного - он хранится у нас и мы не делимся им) и **публичного** (он доступен всем и и спользуется для шифрования данных) 
  
Для генерации SSH-пары можно использовать программу ssh-keygen. Откройте терминал и введите следующую команду.
```BASH
ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" 
```   

 Используйте электронную почту, к которой привязан ваш GitHub-аккаунт.
    Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования ed25519. Ничего страшного: используйте другой алгоритм.

```BASH
ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" 
```  

 После ввода отобразится такое сообщение.
```BASH
Generating public/private rsa key pair.``` # сгенерированы публичный и приватный
```
## Связывем локальный и удаленный репозитории 

1. 

## Схема статусов и жизненого циклов файлов в git 

```mermaid
graph LR;
untracked -- "git add" --> staged;
staged -- "git commit" --> tracked;
staged -- "Изменения" --> modified;
tracked -- "Изменения" --> modified; 
modified -- "git add" --> staged;

```
