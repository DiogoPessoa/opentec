# openSUSE - Guia Básico Pós Instalação  

Este breve guia pós instalação do openSUSE é voltado para iniciantes e irá ajudá-los a instalar alguns softwares e passar informações básicas. 
As instruções que vamos ver a seguir é compatível com as duas versões oficiais do openSUSE: **Leap** (lançamentos periódicos) e **Tumbleweed** (lançamento contínuo).

### CODECS MULTIMÍDIA
A ação a seguir adiciona o repositório **Packman** e instala automaticamente os **codecs** necessários para reprodução de arquivo multimídia no openSUSE Leap e Tumbleweed.

Abra o terminal (ctrl+alt+T) e digite ou cole o comando abaixo:
```sh
$ sudo zypper install opi && sudo opi codecs
```
Se for perguntado se você quer rejeitar a chave, confiar temporariamente ou confiar sempre? [r/t/s/?] - responda com a letra: **s** (sempre).

[OPI - OBS Package Installer](https://github.com/openSUSE/opi)

##### NAVEGADOR CHROMIUM
Instalar com o YaST 1-Click:

* No openSUSE Tumbleweed com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Factory/standard/chromium.ymp?base=openSUSE%3AFactory&query=chromium)

* No openSUSE Leap 15.2 com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Leap:15.2:Update/ports/chromium.ymp?base=openSUSE%3ALeap%3A15.2&query=chromium)

Ou instalar via terminal:
```sh
$ sudo zypper in chromium chromium-ffmpeg-extra
```
##### NAVEGADOR GOOGLE CHROME
No terminal, copie e cole...
1. Adicione o repositório
```sh
$ sudo zypper addrepo http://dl.google.com/linux/chrome/rpm/stable/x86_64 Google-Chrome
```
2. Atualize os repositórios e instale a chave
```sh
$ sudo zypper ref && sudo rpm --import https://dl.google.com/linux/linux_signing_key.pub
```
3. Instale o Google Chrome
```sh
$ sudo zypper in google-chrome-stable
```

### MS TRUETYPE FONTS
Para trabalhos acadêmicos que exigem as normas ABNT, as fontes padronizadas são a Arial ou Times New Roman. Se caso precisar dessas fontes, instale assim:

Instalar com o YaST 1-Click:
* No openSUSE Tumbleweed com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Factory/standard/fetchmsttfonts.ymp?base=openSUSE%3AFactory&query=fetchmsttfonts)
* No openSUSE Leap 15.2 com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Leap:15.2/standard/fetchmsttfonts.ymp?base=openSUSE%3ALeap%3A15.2&query=fetchmsttfonts)

Ou instalar via terminal:
```sh
$ sudo zypper install fetchmsttfonts
```

### UNRAR - EXTRATOR DE ARQUIVOS 
Instalar com o YaST 1-Click:
* No openSUSE Tumbleweed com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Factory/standard/unrar_wrapper.ymp?base=openSUSE%3AFactory&query=unrar_wrapper)
* No openSUSE Leap 15.2 com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Leap:15.2/standard/unrar_wrapper.ymp?base=openSUSE%3ALeap%3A15.2&query=unrar_wrapper)

Ou instalar via terminal:
```sh
sudo zypper install unrar
```

### JAVA JRE (OPENJDK)
Instalar com o YaST 1-Click:
* No openSUSE Tumbleweed com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Factory/standard/java-1_8_0-openjdk.ymp?base=openSUSE%3AFactory&query=java-1_8_0-openjdk)
* No openSUSE Leap 15.2 com [YaST-1-Click](https://software.opensuse.org/ymp/openSUSE:Leap:15.2/standard/java-1_8_0-openjdk.ymp?base=openSUSE%3ALeap%3A15.2&query=java-1_8_0-openjdk)

Ou instalar via terminal:
```sh
sudo zypper in java-1_8_0-openjdk
```

### SUÍTES DE ESCRITÓRIO PARA DESKTOP
O LibreOffice é uma suíte de escritório completa de código aberto compatível com o MS Office. Ele está presente na maioria das Distros Linux, inclusive no openSUSE. 
Abaixo eu cito mais três excelentes alternativas gratuitas. Caso queira instalar algum,  baixe o arquivo **.rpm** que é o pacote de instalação do openSUSE:
* [**ONLYOFFICE**](https://www.onlyoffice.com/pt/download-desktop.aspx): totalmente compatível com os formatos do MS Office, é de código aberto e grátis.
* [**WPS Office**](https://www.wps.com/pt-BR/office/linux): tem uma boa compatibilidade com MS Office, é de código fechado e grátis com anúncios.
* [**FreeOffice**](https://www.freeoffice.com/pt/baixar/aplicativos): também tem boa compatibilidade com MS Office, código fechado e é grátis.

### GERENCIADORES DE PACOTES
* **YaST Software** -  é o principal 	gerenciador de pacote do openSUSE;
* **Discover** - vem por padrão no openSUSE Plasma;
* **GNOME Software** - vem por padrão no GNOME.

Os gerenciadores de pacotes do openSUSE é o lugar mais indicado e confiável para você procurar por softwares.

### SOFTWARE DA COMUNIDADE E TERCEIROS 
Caso o software que você procura não esteja nos repositórios do sistema, você pode pesquisar pelos pacotes mantidos pela comunidade, que são construídos no [openSUSE Build Service](https://en.opensuse.org/Portal:Build_Service).
1. Acesse <https://software.opensuse.org/explore>
2. Pesquise o software desejado, por exemplo: **opera** (navegador de internet)
3. Clique no software que procura
4. Role para baixo e verifique se tem o software para a sua versão do openSUSE
5. Encontrou? Pode clicar em "**1 Click Install**". Esta ação deve abrir o YaST perguntando se você aceita instalar o software.

### HABILITAR O FLATHUB
Habilitando o Flathub teremos softwares de terceiros com formato [FLATPAK](https://www.flatpak.org/) disponíveis para instalar, como: Spotify, XMind, Zoom, Steam e outros. 
Flatpak é um formato de empacotamento e distribuição de softwares em sandbox para Linux.

* Habilite para o Discover Plasma

Abra o Discover → Configuração → Adicionar Flathub

* Habilite para o GNOME Software

Abra o Terminal e cole os comandos abaixo:

Instale o Flatpak
```sh
$ sudo zypper install flatpak
```
2. Adicione o repositório Flathub
```sh
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
3. Reinicie a máquina para completar a instalação.

### DESTAQUES DO OPENSUSE
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
Apenas para demonstração, veremos abaixo alguns comandos do Zypper que podem ser executados no terminal:

```sh
comando | descrição 
$ sudo zypper refresh | atualiza os repositórios 
$ sudo zypper update | (execute no Leap) instala as atualizações
$ sudo zypper dup | (execute no Tumbleweed) instala as atualizações
$ sudo zypper install nome-pacote | instala o pacote
$ sudo zypper remove nome-pacote | remove o pacote
$ sudo zypper repos | lista todos os repositórios
```

Não curtiu muito a linha de comando? Relaxa! Tudo que foi apresentado acima é perfeitamente realizado graficamente pelos gerenciadores de pacotes.

#### Snapper + BTRFS = rollback 😍
No openSUSE você pode fazer um **rollback** (reverte mudanças do sistema para um estado anterior) caso alguma atualização quebre o sistema, por exemplo. Para a mágica acontecer, a partição raiz “/” deve ter sido criada em BTRFS com espaço acima de 16 GB durante a instalação do sistema. 
Caso você utilize EXT4 na raiz, por exemplo, não será possível usufruir do rollback com o Snapper. Isso não se aplica a Home, que pode ser em EXT4, XFS, BTRFS etc.  

No link a seguir você poderá ver uma demonstração detalhada de como fazer um rollback: 
* [Rollback Btrfs no openSUSE - Fast OS](https://fastoslinux.com/2019/11/26/rollback-btrfs-no-opensuse/)

### BEM-VINDO
Leia o “Bem-vindo” do openSUSE!

Assim que o sistema é apresentado, aparece a tela de boas vindas:
```sh
Olá, este é o openSUSE...
```

Nele, você encontrará algumas dicas que já mostrei aqui, como também, documentação de uso, orientações de como instalar drivers da Nvidia, links das comunidades de usuários e mais repositórios de software.. Enfim, aproveite ao máximo o que o openSUSE tem à oferecer e se envolva! 

### REFERÊNCIAS
* [Documentação](https://pt.opensuse.org/Portal:Documentacao)
* [codecs do Packman](https://pt.opensuse.org/SDB:Instalar_codecs_do_Packman)
* [opi/openSUSE](https://github.com/openSUSE/opi)
* [Zypper/Uso](https://pt.opensuse.org/Zypper/Uso) 
* [Snapper](https://en.opensuse.org/openSUSE:Snapper_Tutorial)
* [Flathub](https://flathub.org/home)
* [Grupo no Telegram "openSUSE Brasil"](https://t.me/opensusebr)


