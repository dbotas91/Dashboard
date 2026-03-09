---
dg-publish: "true"
tags:
  - Canon
  - Joomla
  - migração
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

# Guia de Atualização Joomla (3.10.12 para 5.4.3)  
  
Este documento serve como guião para o processo de atualização do site IQC, garantindo a integridade dos dados e a compatibilidade das extensões.
  
---  

## 0. Preparação
Antes de começar é necessário fazer algumas tarefas tais como:
1. Parar a calendarização de artigos.
2. Criar uma página temporária a informar a manutenção do site e colocar o domínio a apontar para essa pasta/ficheiro HTML
	1. Guardar um screenshot da alteração para depois repor.
3. Apagar o atual joomla em staging.iqc.pt
4. Clonar novamente o domínio iqc.pt para o staging.iqc.pt
5. Salvar uma segunda cópia do public_html do joomla para restaurar se for preciso
6. Fazer um segundo backup da BD para restaurar se for preciso
7. Fazer um segundo backup com o Akeeba Backup


## 1. Remoção de pacotes e extensões do joomla
O Joomla tem extensões/pacotes que não são nativos no Joomla.
- É preciso ter uma listagem dos pacotes e extensões que vamos Desinstalar do joomla, uma vez que quase todos não atualizam na versão atual.

Após a remoção das extensões podemos começar a migração.
### Lista de pacotes e extensões
É possível ver a lista de extensões no Joomla ou BD
Pelo Joomla:
- Extensões - Gerir - Gerir (Tem todas as extensões)
- Componentes (lista as extensões instaladas)

Pela BD:
- [SELECT](https://cpanel101.dnscpanel.com:2083/cpsess3865914358/3rdparty/phpMyAdmin/url.php?url=https://dev.mysql.com/doc/refman/8.0/en/select.html) * FROM `fzvai_action_logs_extensions`
- [SELECT](https://cpanel101.dnscpanel.com:2083/cpsess3865914358/3rdparty/phpMyAdmin/url.php?url=https://dev.mysql.com/doc/refman/8.0/en/select.html) * FROM `fzvai_extensions`

#### Confirmação das extensões que têm versões no Joomla 5
As seguintes extensões têm atualizações no Joomla 5:
- [Ações de utilizadores - Historial](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_actionlogs)
- [Akeeba Backup](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_akeeba)
- [Ark Editor](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_arkeditor)
- [Artigos](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_content)
- [Associações multilingues](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_associations)
- [Atualização Joomla!](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_joomlaupdate)
- [Cache](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_cache)
- [Contactos](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_contact)
- [DJ-ImageSlider](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_djimageslider)
- [DPCalendario](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_dpcalendar)
- [Etiquetas](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_tags)
- [Event Gallery](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_eventgallery)
- [Faixas](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_banners)
- [Idiomas](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_languages)
- [Instalador](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_installer)
- [JCE Editor](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_jce)
- [Media](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_media)
- [Mensagens de pós-instalação](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_postinstall)
- [Mensagens](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_messages)
- [Menus](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_menus)
- [Módulos](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_modules)
- [OSMap Free](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_osmap)
- [Pesquisa inteligente](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_finder)
- [Pesquisa](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_search)
- [Plugins](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_plugins)
- [Privacidade](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_privacy)
- [Reencaminhamentos](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_redirect)
- [SEBLOD 3.x](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_cck)
- [SEBLOD Updater](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_cck_updater)
- [Sinais Web](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_newsfeeds)
- [Temas](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_templates)
- [Utilizadores](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_users)
- [Validar](https://iqc.pt/administrator/index.php?option=com_config&view=component&component=com_checkin)

>[!quote]+ Pesquisa pelo Gemini
> **Joomla 5:** É a versão atual e estável.
> **Joomla 6:** Ainda **não foi lançada** (está em fase de planeamento/desenvolvimento), mas o compromisso da equipa do Joomla é manter a compatibilidade com o que funciona no Joomla 5.
> Aqui está a análise da sua lista para o **Joomla 5** (e previsivelmente para o 6):
> ### 1. Componentes Nativos (Existem sempre)
> 
> Estes fazem parte do "core" do Joomla e continuam a existir nas versões 5 e 6:
>  - **Artigos** (com_content)
>  - **Associações multilingues** (com_associations)    
>  - **Atualização Joomla!** (com_joomlaupdate)
>  - **Cache** (com_cache)
>  - **Contactos** (com_contact)
>  - **Etiquetas** (com_tags)
>  - **Faixas / Banners** (com_banners)    
>  - **Idiomas** (com_languages)
>  - **Instalador** (com_installer)
>  - **Media** (com_media)
>  - **Mensagens de pós-instalação** (com_postinstall)
>  - **Mensagens** (com_messages)
>  - **Menus** (com_menus)
>  - **Módulos** (com_modules)
>  - **Pesquisa inteligente** (com_finder) - _Nota: Este é o padrão agora._
>  - **Plugins** (com_plugins)
>  - **Privacidade** (com_privacy)
>  - **Reencaminhamentos** (com_redirect)
>  - **Sinais Web / Newsfeeds** (com_newsfeeds)
>  
>  ### 2. Componentes de Terceiros compatíveis com Joomla 5
>  Estes componentes são externos, mas já têm versões que funcionam no Joomla 5:
>  - **Akeeba Backup:** Sim, existe a versão 9/10 totalmente compatível.
>  - **JCE Editor:** Sim, a versão Pro e Core são compatíveis.
>  - **DPCalendar:** Sim, existe versão para Joomla 5.
>  - **OSMap Free:** Sim, a Joomlashack atualizou o OSMap para o Joomla 5.
>  - **DJ-ImageSlider:** Sim, existe versão compatível com Joomla 4/5.
>  - **Event Gallery:** Sim, o programador (Sven Bluege) mantém compatibilidade com Joomla 5.    
>  ### 3. Componentes com Problemas ou Descontinuados
>  - **Pesquisa (com_search):** **NÃO** existe nativamente no Joomla 5. Foi removida em favor da _Pesquisa Inteligente (com_finder)_. Se precisar dela, tem de instalar um pacote de compatibilidade à parte, mas é recomendado migrar para a Pesquisa Inteligente.
>  - **Ark Editor:** O desenvolvimento tem sido muito lento nos últimos anos. Embora possa funcionar com o plugin de compatibilidade (Backward Compatibility), não é recomendado para instalações novas no Joomla 5; a maioria dos utilizadores migrou para o JCE ou para o editor nativo (TinyMCE).
>  - **SEBLOD 3.x / Updater:** Este é o ponto mais crítico. O SEBLOD teve muitas dificuldades na transição para o Joomla 4 e 5. Embora existam versões beta/recentes para o Joomla 4, a sua utilização no Joomla 5 é complexa e pode exigir o plugin de compatibilidade ativado. Não é garantido que funcione no futuro Joomla 6 sem uma reconstrução profunda.
> 
> **Resumo:** Quase todos os componentes da sua lista existem ou têm substitutos diretos no **Joomla 5**. As únicas exceções que exigem atenção redobrada ou substituição são a **Pesquisa antiga (com_search)**, o **Ark Editor** e, especialmente, o **SEBLOD**.

Após a confirmação dos plugins que serão atualizados para depois instalar novamente, é necessário *remover* pacotes, plugins, componentes que não são feitos no Joomla.

## 2. Atualização do joomla
Ao remover as extensões que não são parte do Joomla, podemos proceder à atualização do mesmo.

A atualização do Joomla é acedida através de:
Componentes → Atualização Joomla!

Este é o componente para fazer a atualização do Joomla!.
O componente irá fazer uma verificação geral de todas as extensões para verificar a compatibilidade com o Joomla! 4 indicando:
- Falhas nas verificações de extensões de pré-atualização. Dá informações como “Não foi possível verificar a compatibilidade destes plugins. O pedido ao servidor de atualização expirou ou foi devolvido um erro.”
- Não estão disponíveis informações sobre a atualização. Dá informações como “A extensão não disponibiliza uma versão compatível com a versão escolhida do Joomla. Isso pode significar que a extensão não usa o sistema de atualização do Joomla ou o seu programador ainda não disponibilizou informações de compatibilidade para esta versão do Joomla.”
- Se estiver tudo bem, tem apenas a informação “Nenhuma atualização necessária”

Feita a verificação, seguimos para o separador “Atualização em linha”. 
Aqui podem existir alertas como:
>[!warning]- Alerta
> Existem plugins instalados e ativados que podem interferir com a atualização do Joomla e resultar numa falha de atualização que deixa o sítio inacessível.  
> 
> Você é fortemente aconselhado a atualizar, desativar ou desinstalar esses plugins antes de atualizar o Joomla.

E/ou também
>[!attention]- Os seguintes plugins podem provocar problemas durante a atualização
>|Plugin|Pacote|Dados de autor|URL do autor da extensão|
|---|---|---|---|
|System - Helix3 Framework||JoomShaper.com|[http://www.joomshaper.com Abrir em nova janela](http://www.joomshaper.com/)|
|Event Gallery - Google Photos and Flickr Updater|Event Gallery Core - Package|Sven Bluege|[www.svenbluege.de Abrir em nova janela](https://iqc.pt/administrator/www.svenbluege.de)|
|System - JCE|JCE Extension Package|Ryan Demmer|[http://www.joomlacontenteditor.net Abrir em nova janela](http://www.joomlacontenteditor.net/)|
|System - SEBLOD|SEBLOD (App Builder & CCK)|Octopoos|[https://www.seblod.com Abrir em nova janela](https://www.seblod.com/)|
|User - SEBLOD|SEBLOD (App Builder & CCK)|Octopoos|[https://www.seblod.com Abrir em nova janela](https://www.seblod.com/)|
|Event Gallery - Capabilities Report|Event Gallery Core - Package|Sven Bluege|[www.svenbluege.de Abrir em nova janela](https://iqc.pt/administrator/www.svenbluege.de)|
|System - Typography by ARK|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Joomla Media Manager Extension|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Inline content editing|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - ARK Versions|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Inline HTML Module Versioning|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Reset SEF Base|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - ArkEditor Modal plugin|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - ARK k2ExtraFields|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Inline History|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Ark Bootstrap|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - ArkMedia Table Observer|Package Ark Editor|WebxSolution Ltd|[http://www.arkextensions.com Abrir em nova janela](http://www.arkextensions.com/)|
|System - Joomlashack Extension Support||Joomlashack|[https://www.joomlashack.com Abrir em nova janela](https://www.joomlashack.com/)|
|Event Gallery - Console Plugin|Event Gallery Core - Package|Sven Bluege|[www.svenbluege.de Abrir em nova janela](https://iqc.pt/administrator/www.svenbluege.de)|
|User - DPCalendar|DPCalendar|Digital Peak|[joomla.digital-peak.com Abrir em nova janela](https://iqc.pt/administrator/joomla.digital-peak.com)|
|System - Akeeba extensions version check|Akeeba Backup package|Nicholas K. Dionysopoulos|[https://www.akeeba.com](https://www.akeeba.com/)|

Haverá uma mensagem no final num checkbox a informar “Deseja ignorar os avisos sobre plugins potencialmente incompatíveis e continuar com a atualização?”. 

Teremos de clicar no checkbox e clicar no botão “Instalar atualização” para proceder à atualização.
