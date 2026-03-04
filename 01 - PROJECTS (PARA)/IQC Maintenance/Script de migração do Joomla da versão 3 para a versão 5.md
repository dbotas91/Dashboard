# Guia de Atualização Joomla (3.10.12 para 5.4.14)  
  
Este documento serve como guião para o processo de atualização do site IQC, garantindo a integridade dos dados e a compatibilidade das extensões.
  
---  

## 0. Preparação
Antes de começar é necessário fazer algumas tarefas tais como:
1. Parar a calendarização de artigos.
2. Apagar o atual joomla em staging.iqc.pt
3. Clonar novamente o domínio iqc.pt para o staging.iqc.pt
4. Salvar uma segunda cópia do public_html do joomla para restaurar se for preciso
5. Fazer um segundo backup da BD para restaurar se for preciso
6. Criar uma página temporária a informar a manutenção do site e colocar o domínio a apontar para essa pasta/ficheiro HTML
	1. Guardar um screenshot da alteração para depois repor.

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

