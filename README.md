# suporte - Python 3.9
Um Chatbot como suporte para colocar em sua VPS! | A chatbot as suport to put in your VPS!

## How does it work | Como isso funciona
After installing Selenium, Chatterbot and Flask, configure this chatbot and enjoy | Após instalar o Selenium, Chatterbot e Flask, configure este chatbot e divirta-se.

* Configurando na inicialização do sistema
```
sudo nano /lib/systemd/system/suporte.service
```
Copie e cole o script do arquivo que corresponde ao arquivo criado na VPS (Não esqueça de mudar os caminhos)
```
[Unit]
Description=My Script Service
After=multi-user.target

[Service]
Type=idle
ExecStart=/usr/bin/python3 /var/www/suporte/app.py > /var/www/suporte/suporte.log 2>&1
Environment="PYTHONPATH=$PYTHONPATH:/home/ubuntu/.local/lib/python3.6/site-packages/"

[Install]
WantedBy=multi-user.target
```
Comando acima é para configurar saida de logs
```
sudo chmod 644 /lib/systemd/system/suporte.service
```
```
sudo systemctl daemon-reload && sudo systemctl enable suporte.service
```
Comando acima habilita o arquivo no systemd
```
sudo reboot
```
```
sudo systemctl status suporte.service
```
-----------------------------------------------
### Contributing | Contribuindo
* Contributions are welcome! Please read our guide before contributing to help this project | As contribuições são bem-vindas! Por favor, leia nosso guia antes de contribuir para ajudar este projeto.
### Referências
* Todos os scripts contém biblioteca Chatterbot e Microframework Flask
* pip install ChatterBot
* pip install Flask
* https://chromedriver.chromium.org/downloads
* https://stackoverflow.com/questions/35641414/python-import-of-local-module-failing-when-run-as-systemd-systemctl-service
* https://pt.stackoverflow.com/questions/402231/como-executar-programa-em-python-ao-iniciar-linux-mint
