# Nexus CLI
# Установка и обновление ноды Nexus

## Требования
- **Linux (Ubuntu 20.04/22.04, Debian 11+)**
- **4 CPU / 8 RAM **


---

### 1️ Установка зависимостей
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl jq screen -y
```

### 2️⃣ Установка Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

### 3️⃣ Запуск ноды в `screen`
```bash
screen -S nexus
nexus node start
```
> ⚠️ Нажмите `Ctrl + A`, затем `D`, чтобы выйти из `screen` (нода продолжит работать в фоне).

### 4️⃣ Проверка статуса ноды
```bash
nexus node status
```

---

## 🔄 Обновление ноды Nexus
### 1️⃣ Остановка ноды
```bash
screen -r nexus   # Войти в screen
nexus node stop   # Остановить ноду (если команда доступна)
exit              # Выйти из screen
```

### 2️⃣ Удаление старой версии
```bash
rm -rf ~/.nexus
rm -f /usr/local/bin/nexus
```

### 3️⃣ Установка новой версии
```bash
curl https://cli.nexus.xyz/ | sh
```

### 4️⃣ Перезапуск ноды в `screen`
```bash
screen -S nexus
nexus node start
```

### 5️⃣ Проверка работы ноды
```bash
nexus node status
```

---

## 🛠 Полезные команды

 **Проверить процессы Nexus:**
```bash
ps aux | grep nexus
```

 **Просмотреть логи в реальном времени:**
```bash
tail -f ~/.nexus/logs/nexus.log
```

 **Переподключиться к `screen` с нодой:**
```bash
screen -r nexus
```

 **Отключиться от `screen` без остановки ноды:**
```bash
Ctrl + A, затем D
```

  **Остановить `screen` (если нужно удалить сессию):**
```bash
screen -XS nexus quit
```

---

