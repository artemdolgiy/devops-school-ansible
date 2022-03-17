# Описание процесса создания зашифрованного файла с данными создаваемых пользователей

## 1. Создадим файл `users.yml`

```yaml
users:
  user1:
    username: alice
    homedir: /home/alice
    comment: alice@example.com
    password: alice_password
  user2:
    username: bob
    homedir: /home/bob
    comment: bob@example.com
    password: bob_password
  user3:
    username: carol
    homedir: /home/carol
    comment: carol@example.com
    password: carol_password
```

## 2. Зашифруем файл

`ansible-vault encrypt --vault-password-file vault_passwd users.yml`

## 3. Теперь плэйбук необходимо запускать с вводом пароля от хранища

с запросом пароля `ansible-playbook --ask-vault-pass create_users.yml`

или

с указанием имени файла, в котором хранится пароль от хранилища `ansible-playbook --vault-password-file vault_passwd create_users.yml`
