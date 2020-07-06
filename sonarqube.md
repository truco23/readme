# Sonarcube


### instalação com docker

__docker container run -d --name sonarqube -p 9000:9000 sonarqube__ => iniciando sonarqube na porta 9000

__analisar como rodar sonar-scanner pelo docker__

__sonar-scanner__ => na pasta do projeto rodar o bat funciona de tiver sonnar-scanner local extraido em c:


### intalação local

- fazer download sonarcube
- fazer download scanner
- extrair no diretório c: (do contrário criar variável de ambiente)
- executar bat sonarqube
    c:\sonarqube\sonarqube-8.3.1.34397\bin\windows-x86-64\tartsonar.bat
- na pasta do projeto rodar o bat sonar-scanner
    c:\sonarqube\sonar-scanner-4.3.0.2102-windows\bin\sonar-scanner.bat