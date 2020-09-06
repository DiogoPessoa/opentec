# Guia básico pós instalação do openSUSE 

Este breve guia pós instalação do openSUSE é voltado para iniciantes e irá ajudar a instalar alguns softwares e passar informações básicas. 
As instruções que vamos ver a seguir é compatível com as duas versões oficiais do openSUSE: **Leap** (lançamentos periódicos) e **Tumbleweed** (lançamento contínuo).

### Instalar codecs multimídia
A ação a seguir adiciona o repositório **Packman** e instala automaticamente os **codecs** necessários para reprodução de arquivo multimídia.
##### Para o Leap e Tumbleweed 
No terminal:
```sh
$ sudo zypper install opi
$ sudo opi codecs
```
[OPI:](https://github.com/openSUSE/opi) OBS Package Installer

### Instalar o Chromium ou Google Chrome
##### Navegador Chromium
No terminal:
```sh
$ sudo zypper in chromium chromium-ffmpeg-extra
```
##### Navegador Google Chrome
No terminal:
1. Adicione o repositório
```sh
$ sudo zypper addrepo http://dl.google.com/linux/chrome/rpm/stable/x86_64 Google-Chrome
```
2. Atualize os repositórios
```sh
$ sudo zypper ref
```
3. Instale a chave pública
```sh
$ sudo rpm --import https://dl.google.com/linux/linux_signing_key.pub
```
4. Instale o Google Chrome
```sh
$ sudo zypper in google-chrome-stable
```

### Instalar MS Truetype fonts
Para trabalhos acadêmicos que exigem as normas ABNT, as fontes padronizadas são a Arial ou Times New Roman. Se caso precisar dessas fontes, instale assim:
No terminal:
```sh
$ sudo zypper install fetchmsttfonts
```

### Descompactador de arquivos 
No terminal:
```sh
sudo zypper install unrar
```

### Instalar Java JRE
No terminal:
```sh
sudo zypper in java-1_8_0-openjdk
```
Veja a versão do instalada abrindo o terminal e digite:  
```sh 
$ java -version
```

### Suíte de escritório para desktop
O LibreOffice é uma suíte de escritório completa de código aberto compatível com o MS Office. Ele está presente na maioria das Distros Linux, inclusive no openSUSE. 
Abaixo eu cito mais três excelentes alternativas gratuitas. Caso queira instalar algum,  baixe o arquivo **.rpm** que é o pacote de instalação do openSUSE:
* **ONLYOFFICE**: totalmente compátivel com os formatos do MS Office, é de código aberto e grátis.
[Baixe o ONLYOFFICE](https://www.onlyoffice.com/pt/download-desktop.aspx)
* **WPS Office**: tem uma boa compatibilidade com MS Office, é de código fechado e grátis com anúncios.
[Baixe o WPS Office](https://www.wps.com/pt-BR/office/linux)
* **FreeOffice**: também tem boa compatibilidade com MS Office, código fechado e é grátis.
[Baixe o FreeOffice](https://www.freeoffice.com/pt/baixar/aplicativos)

### Gerenciadores de pacotes
* **YaST Software** -  é o principal 	gerenciador de pacote do openSUSE
* **Discover** - vem por padrão no openSUSE Plasma
* **GNOME Software** - vem por padrão no GNOME

Os gerenciadores de pacotes do openSUSE é o lugar mais indicado e confiável para você procurar por softwares.

### Software da comunidade e de terceiros 
Caso o software que você procura não esteja nos repositórios do sistema, você pode pesquisar pelos pacotes mantidos pela comunidade, que são construídos no [openSUSE Build Service](https://en.opensuse.org/Portal:Build_Service).
1. Acesse [https://software.opensuse.org/explore]
2. Pesquise o software desejado, por exemplo: **opera** (navegador de internet)
3. Clique no software que procura
4. Role para baixo e verifique se tem o software para a sua versão do openSUSE
5. Encontrou? Pode clicar em "**1 Click Install**". Esta ação deve abrir o YaST perguntando se você aceita instalar o software.

### Habilitar o Flathub
Habilitando o Flathub teremos softwares de terceiros com formato [FLATPAK](https://www.flatpak.org/) disponíveis para instalar, como: Spotify, XMind, Zoom, Steam e outros. 
Flatpak é um formato de empacotamento e distribuição de softwares em sandbox para Linux.
* Habilite para o Plasma Discover
    * Abra: Discover → Configuração → Adicionar Flathub
* Habilite para o GNOME Software
    * Abra: GNOME Software → Instalados → Programas → e marque a caixa de seleção “Suporte a flatpak”.
##### Resolução de problema para ativar o Flathub
Caso você tenha problema durante o processo de habilitar o Flathub, provavelmente a solução está a seguir:
No terminal
```sh
sudo rm -rf /var/lib/flatpak/repo
```
Agora tente adicionar novamente o Flathub.

### Destaques do openSUSE
#### YaST 
É a ferramenta para administração do sistema e se destaca por sua facilidade de uso, possibilitando instalar e customizar rapidamente o sistema com alguns cliques.
Algumas funções:
* Gerenciar repositórios de software
* Adicionar impressora
* Formatar e particionar unidades
* Editar o booting/GRUB
* Configurar firewall
#### ZYPPER
É um poderoso gerenciador de pacotes de linha de comando. 
Vamos ver alguns comandos do Zypper para se familiarizar com a linha de comando no terminal:
| comando | descrição |
| ------- | --------- |
| $ sudo zypper refresh | atualiza os repositórios |
| $ sudo zypper update | (execute no Leap) instala as atualizações |
| $ sudo zypper dup | (execute no Tumbleweed) instala as atualizações |
| $ sudo zypper install NOME | instala o pacote |
| $ sudo zypper remove NOME | remove o pacote |
| $ sudo zypper repos | lista todos os repositórios |
#### Snapper + BTRFS = rollback 😍
No openSUSE você pode fazer um **rollback** (reverte mudanças do sistema para um estado anterior) caso alguma atualização quebre o sistema, por exemplo. Para a mágica acontecer, a partição raiz “/” deve ter sido criada em BTRFS com espaço acima de 16 GB durante a instalação do sistema. 
Caso você utilize EXT4 na raiz, por exemplo, não será possível usufruir do rollback com o Snapper. Isso não se aplica a Home, que pode ser em EXT4, XFS, BTRFS etc.  

No link a seguir você poderá ver uma demonstração detalhada de como fazer um rollback: [fastoslinux.com](https://fastoslinux.com/2019/11/26/rollback-btrfs-no-opensuse/)

### ''Bem-vindo''
Leia o “Bem-vindo” do openSUSE!
Nele você encontrará algumas dicas que já mostrei aqui, como também, orientações de como instalar drivers da Nvidia, documentação de uso, links das comunidades de usuários e mais repositórios de software. Enfim, aproveite ao máximo o que o openSUSE tem à oferecer e se envolva!

### Notas
Eu sou apenas um usuário relativamente novo do openSUSE com a intenção de facilitar a transição de novos usuários. 

### Referências
* Documentação
[https://pt.opensuse.org/Portal:Documentacao]
* Codecs do Packman
[https://pt.opensuse.org/SDB:Instalar_codecs_do_Packman]
* opi/openSUSE
[https://github.com/openSUSE/opi]
* Zypper/Uso
[https://pt.opensuse.org/Zypper/Uso] 
* Snapper
[https://en.opensuse.org/openSUSE:Snapper_Tutorial]
* Flathub
[https://flathub.org/home]
* Grupo no Telegram #openSUSE Brasil
[https://t.me/opensusebr]


