# Linux

## Requirements

# Tasks: 
1. Get context from URL.
```
curl -O https://github.com/Oollll/Working-repository-training-project-/README.md
```

2. Check CPU, memory, network, disks.
```
- lscpu
- free -h
- ip a
- df -h
```

3. Add user and add to sudo group.
```
- sudo adduser username
- sudo usermod -aG sudo username

```

4. Create file and change permissions for only sudo user access (read | write). 
```
- touch test.txt
- sudo chown root:root test.txt
- sudo chmod 600 test.txt 
you can also use this command 
- sudo chmod u=rw test.txt
```

5. Writing an installation program bash script.
    - Atom or other IDE.
    - Checking program availability. 
    - Use logical operators. (if, else etc)
```
#!/bin/bash

# Перевірка наявності програми Visual Studio Code
if command -v code &> /dev/null; then
    echo "Visual Studio Code вже встановлено на вашій системі."
else
    echo "Visual Studio Code не виявлено на вашій системі."
    echo "Встановлюємо Visual Studio Code через завантаження .deb файлу..."
    # Завантаження останньої версії Visual Studio Code для arm64 з офіційного сайту
    wget -O vscode.deb https://update.code.visualstudio.com/latest/linux-deb-arm64/stable
    # Встановлення Visual Studio Code з завантаженого deb-файлу
    sudo dpkg -i vscode.deb
    # Видалення завантаженого deb-файлу
    rm vscode.deb
fi
```
5.1. Run script 
```
bash install_code.sh
```
