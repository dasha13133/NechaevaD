1) Откройте Терминал. Вставьте в него следующий код, подставив в кавычки свой адрес электронной почты на GitHub.
ssh-keygen -t ed25519 -C "your_email@example.com"
Эта команда создает новый ключ SSH, используя введенный адрес электронной почты.
> Generating public/private ed25519 key pair.
После вам будет предложено ввести название файла, в который сохранится ключ. Нажмите Enter, чтобы принять предложенное название и
расположение файла по умолчанию.
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
Не используйте пароль при генерации ключа
> Enter passphrase (empty for no passphrase): [Press enter]
> Enter same passphrase again: [Press enter]
2) Добавление ключа в ssh-агент
Запустите в терминале shh-agent.
eval "$(ssh-agent -s)"
> Agent pid 59566
Добавьте свой приватный ключ SSH в ssh-agent. Если вы создали свой ключ под другим именем, замените id_ed25519 в команде именем вашего
приватного ключа.
$ ssh-add ~/.ssh/id_ed25519
Добавление ключа на сайт
Откройте настройки пользователя (Settings) и выберите раздел SSH and GPG keys, или перейдите по ссылке https://github.com/settings
/keys.
Кликните на New SSH key или Add SSH key.
В поле «Title» добавьте описание нового ключа. 
Вставьте ключ из буфера обмена в поле Key
Нажмите "Add SSH key". Если будет предложено, введите пароль для подтверждения
3) Когда вы решите склонировать репозиторий, нужно нажать кнопку Clone, но вместо HTTPS выбрать SSH. Скопировать ссылку и выполнить
команду git clone "скопированная ссылка"