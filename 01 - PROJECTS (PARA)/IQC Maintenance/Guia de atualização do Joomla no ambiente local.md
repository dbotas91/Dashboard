---
dg-publish: "true"
tags:
  - Canon
  - Joomla
mature-status: canon
created: 2026-03-04 11:58
dg-note-icon: canon
noteIcon: canon
updated: 2026-03-04 11:58
dgPassFrontmatter: "true"
---
[[Home|Back home]]
Status: [[Canon]]
Tags:  [[Joomla!]]

# Guia de Atualização Joomla (3.x para 5.4)  
  
Este documento serve como guião para o processo de atualização do site IQC, garantindo a integridade dos dados e a compatibilidade das extensões.  
  
---  
  
## 0. Limpeza do Ambiente (Preparação)  
Antes de começar, é necessário remover as instalações antigas do XAMPP para evitar conflitos de portas e permissões.  
  
**Pastas identificadas para remoção em `/opt`:**  
- `/opt/lampp`  
- `/opt/lampp_7.4_backup`  
- `/opt/lampp_8.0_backup`  
  
**Comando de limpeza (executar no terminal):**  
```bash  
sudo rm -rf /opt/lampp /opt/lampp_7.4_backup /opt/lampp_8.0_backup  
```  
  
---  
  
## 1. Preparação do Ambiente Local  
1. **Download e Instalação do XAMPP 8.0.30:**  
   - Descarregar o instalador via terminal:  
```bash
wget https://sourceforge.net/projects/xampp/files/XAMPP%20Linux/8.0.30/xampp-linux-x64-8.0.30-0-installer.run/download -O xampp-linux-x64-8.0.30-0-installer.run  
```
 - Dar permissão de execução:  
  ```bash  
  chmod +x xampp-linux-x64-8.0.30-0-installer.run  
  ```   
    
- Executar o instalador (como root):  
```bash  
     sudo ./xampp-linux-x64-8.0.30-0-installer.run  
```
   - Siga os passos no ecrã para completar a instalação em `/opt/lampp`.  
  
2. **Download do Site (via lftp):**  
   - Para descarregar o `public_html`:  
```bash  
     lftp -u 'dapb@iqc.pt' -e "set ssl:verify-certificate no; mirror --verbose /public_html /home/dariobotas/iqc/public_html_local; quit" ftp.iqc.pt
```   
 Irá pedir a senha de ftp e depois irá descarregar os ficheiros para a pasta indicada no /home/dariobotas …
 - Para descarregar a Base de Dados (Dump SQL):  
```bash  
     lftp -u 'utilizador','password' -e "get iqc_antes_update.sql; quit" ftp.iqc.pt  
```
3. **Restauro do Site:**  
   - Colocar os ficheiros em `/opt/lampp/htdocs/`.  
   - Importar o `.sql` via phpMyAdmin ou CLI.  
     - sudo nano /opt/lampp/etc/php.ini  
       - Dentro do ficheiro, usa Ctrl + W para procurar as seguintes variáveis e altera os valores para o tamanho que desejares (exemplo: 100M para 100 Megabytes):  
       upload_max_filesize: Define o tamanho máximo do ficheiro.  
         
       upload_max_filesize = 100M  
         
       post_max_size: Deve ser igual ou maior que o valor acima.  
         
       post_max_size = 100M  
         
       memory_limit: Deve ser superior ao post_max_size.  
         
       memory_limit = 128M  
         
       max_execution_time: (Opcional) Aumenta o tempo para evitar que o import pare a meio.  
         
       max_execution_time = 300  
         
       [!IMPORTANT]  
       Se o teu ficheiro SQL for muito grande (ex: 500MB+), às vezes é melhor usar a linha de comando para importar em vez do phpMyAdmin.  

	   Reiniciar o apache com sudo /opt/lampp/lampp restart  
	    
       ##### Uma alternativa (Se não quiseres editar o PHP)  
       Se não puderes reiniciar o servidor ou quiseres algo mais rápido, podes tentar criar (ou editar) um ficheiro chamado .htaccess na pasta raiz do teu phpMyAdmin (/opt/lampp/phpmyadmin/) e adicionar:  
  
       php_value upload_max_filesize 100M  
       php_value post_max_size 100M  
         
       ##### Importar .sql via Terminal Linux
       Importar via linha de comandos (CLI) é a melhor escolha, especialmente para ficheiros grandes, porque ignora os limites de tempo e de tamanho do PHP/Apache.  
         
       Como estás a usar o XAMPP/LAMPP no Linux (/opt/lampp/), o comando deve ser executado apontando para os binários do XAMPP.         
       A Base de Dados deve existir: O comando acima não cria a base de dados automaticamente. 
       Se ainda não a criaste, faz primeiro:       
       
       /opt/lampp/bin/mysql -u root -p -e "CREATE DATABASE meu_site;"  
       
       ###### O Comando Base          
       Abre o terminal e utiliza a seguinte estrutura:          /opt/lampp/bin/mysql -u [utilizador] -p [nome_da_base_de_dados] < /caminho/para/o/teu/ficheiro.sql                 
       - Acompanhar o progresso: O MySQL não mostra uma barra de progresso por defeito. Se o ficheiro for gigante e o terminal parecer "congelado", não te preocupes, ele está a trabalhar. Quando terminar, o terminal voltará a mostrar a linha de comandos.  
	       - Erros de Caracteres (UTF-8): Se tiveres problemas com acentos após a importação, adiciona o parâmetro de encoding:
		   /opt/lampp/bin/mysql --default-character-set=utf8 -u root -p meu_site < ficheiro.sql  
		   - Configurar o `configuration.php` local.  
		   - Validar que o site carrega e que o acesso ao `/administrator` está funcional.  
  
---  
  
## 2. Inventário e Limpeza (Joomla 3.10.x)  
1. **Listagem de Extensões:**  
   - Aceder a *Extensions -> Manage -> Manage*.
   - Aceder a *Extensões -> Gerir -> Gerir*.
   - Criar uma lista de todas as extensões instaladas.  
2. **Remoção de "Lixo":**  
   - Desinstalar todas as extensões que não são nativas do Joomla (`Core`).  
   - Focar especialmente em plugins de sistema, componentes de terceiros e templates antigos.  
   - **Importante:** Plugins antigos de PHP 5/7 podem causar erros fatais (WSOD) na atualização.  
3. **Backup Intermédio:** Realizar um dump da base de dados e ficheiros após a limpeza.  
  
---  
  
## 3. Primeira Atualização (Joomla 4.4.14)  
1. **Update:** Utilizar o componente *Joomla Update*.  
2. **Destino:** Joomla 4.4.14 (versão estável de ponte).  
3. **Verificação:** Testar navegação básica e erros de PHP.  
  
---  
  
## 4. Atualização de Infraestrutura (PHP 8.2.12)  
1. **PHP Update:** Atualizar o XAMPP ou o binário do PHP para a versão 8.2.12.  
2. **Compatibilidade:** O Joomla 4.4 e 5 requerem versões superiores de PHP.  
  
---  
  
## 5. Correção de Template e Estética  
1. **Template:** Resolver conflitos de CSS/JS (Bootstrap 5).  
2. **Overrides:** Verificar se os ficheiros em `templates/[nome-template]/html` precisam de ajuste.  
  
---  
  
## 6. Salto Final (Joomla 5.4)  
1. **Update:** Atualizar do 4.4.14 para o Joomla 5.4.  
2. **Plugin de Retrocompatibilidade:** Ativar se necessário.  
3. **Validação:** Verificar formulários, menus e integrações críticas.  
  
---  
  
## 7. Reinstalação e Finalização  
1. **Plugins Necessários:** Consultar a lista inicial e instalar as versões compatíveis com Joomla 5.  
2. **Limpeza Final:** Remover ficheiros temporários e otimizar tabelas da DB.  
  
---  
*Nota: Realizar backups em cada passo bem-sucedido.*