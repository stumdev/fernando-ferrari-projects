# Documentação do Projeto de Padronização e Gerenciamento de Computadores

## Sumário

* [Visão Geral](#visão-geral)
* [Objetivo](#objetivo)
* [Estrutura dos Pendrives](#estrutura-dos-pendrives)
* [Ambiente Atual](#ambiente-atual)
* [Preparação da Máquina Modelo](#preparação-da-máquina-modelo)
* [Criação da Imagem](#criação-da-imagem)
* [Backup das Imagens](#backup-das-imagens)
* [Implantação nas Demais Máquinas](#implantação-nas-demais-máquinas)
* [Procedimento de Restauração](#procedimento-de-restauração)
* [Estado Atual do Projeto](#estado-atual-do-projeto)
* [Próximos Passos](#próximos-passos)

---

# Visão Geral

Este repositório tem como finalidade documentar todos os procedimentos relacionados à preparação, padronização, clonagem e restauração dos computadores utilizados no projeto desenvolvido na Escola Estadual de Ensino Médio Fernando Ferrari.

Além da documentação dos processos atuais, este repositório servirá futuramente como base para registrar o desenvolvimento do software de gerenciamento remoto que está sendo criado pela equipe.

O objetivo desse software será permitir a administração centralizada dos computadores da escola, reduzindo alterações indevidas realizadas pelos usuários, como:

* alteração do papel de parede;
* instalação de programas não autorizados;
* mudanças em configurações do sistema;
* modificações que comprometam a padronização das máquinas.

Esta documentação deve ser mantida atualizada para que qualquer integrante consiga continuar o projeto mesmo na ausência dos responsáveis atuais.

---

# Objetivo

O processo foi criado para reduzir o tempo gasto com formatações e garantir que todos os computadores de um mesmo modelo permaneçam exatamente iguais.

Ao invés de instalar e configurar cada computador manualmente, uma única máquina é preparada completamente e utilizada como referência para gerar uma imagem do sistema.

Essa imagem é restaurada nas demais máquinas utilizando o Clonezilla, garantindo padronização e economia de tempo.

Entre as vantagens desse método estão:

* redução significativa do tempo de implantação;
* padronização completa das máquinas;
* facilidade para manutenção;
* rápida recuperação em caso de falhas;
* facilidade para novos integrantes compreenderem o processo.

---

# Estrutura dos Pendrives

Atualmente a equipe possui dez pendrives destinados às seguintes funções:

| Pendrive       | Finalidade                                  |
| -------------- | ------------------------------------------- |
| Windows 11 (1) | Instalação do Windows 11                    |
| Windows 11 (2) | Instalação do Windows 11                    |
| Windows 11 (3) | Instalação do Windows 11                    |
| Windows 11 (4) | Instalação do Windows 11                    |
| Windows 10 (1) | Instalação do Windows 10                    |
| Windows 10 (2) | Instalação do Windows 10                    |
| Ubuntu         | Instalação do Ubuntu                        |
| Clonezilla     | Inicialização do Clonezilla                 |
| Armazenamento  | Armazena as imagens criadas pelo Clonezilla |
| Office         | Instalação do Microsoft Office              |

Cada pendrive possui uma função específica e deve permanecer organizado para evitar erros durante as instalações.

---

# Ambiente Atual

Até o momento, o procedimento foi aplicado em três notebooks do seguinte modelo:

**HP 240 G7**

Todos possuem a mesma configuração de hardware, permitindo utilizar uma única imagem para restaurar qualquer equipamento desse modelo.

Caso futuramente sejam adicionados computadores com hardware diferente, uma nova imagem deverá ser criada especificamente para aquele modelo.

---

# Preparação da Máquina Modelo

Foi escolhido um notebook HP 240 G7 para servir como máquina de referência.

Todo o processo abaixo foi realizado apenas nessa máquina.

## 1. Instalação do sistema operacional

Foi realizada uma instalação limpa do Windows 10.

---

## 2. Configuração inicial

Após a instalação do Windows foram realizadas as configurações iniciais necessárias para utilização do equipamento.

No momento, a máquina permanece sem senha de acesso, facilitando o processo de implantação.

---

## 3. Instalação dos programas

Os softwares utilizados pela escola foram instalados utilizando o Ninite.

Essa ferramenta permite instalar diversos programas automaticamente, reduzindo o tempo de configuração.

---

## 4. Instalação dos drivers

Após a instalação dos programas, todos os drivers foram instalados utilizando o DriverHub.

Antes de prosseguir para a próxima etapa, foi verificado que nenhum dispositivo permanecia com drivers pendentes.

---

## 5. Limpeza e otimização

Com o sistema totalmente funcional, foi executado o Windows10Debloater.

Essa etapa remove aplicativos desnecessários instalados junto ao Windows (bloatware), reduz processos em segundo plano e melhora o desempenho geral do sistema.

A limpeza somente deve ser realizada após confirmar que todos os drivers e programas necessários estão funcionando corretamente.

---

# Criação da Imagem

Após concluir toda a configuração da máquina modelo, foi utilizado o Clonezilla para criar uma imagem completa do disco.

Essa imagem foi armazenada no pendrive destinado exclusivamente ao armazenamento das imagens.

A partir desse momento, essa imagem passa a ser considerada a instalação padrão para notebooks HP 240 G7.

Sempre que forem realizadas alterações significativas na configuração da máquina modelo, recomenda-se gerar uma nova imagem para manter o padrão atualizado.

---

# Backup das Imagens

Como medida de segurança, todas as imagens armazenadas no pendrive de armazenamento também possuem uma cópia no servidor da escola.

Caso o pendrive de armazenamento seja perdido, danificado ou apresente qualquer outro problema, **não é necessário recriar as imagens**, desde que a cópia existente no servidor esteja íntegra.

Nessa situação, a imagem poderá ser recuperada diretamente pela rede e copiada novamente para um pendrive de armazenamento ou utilizada conforme a infraestrutura disponível.

Antes de iniciar qualquer processo de criação de uma nova imagem, sempre verifique se já existe uma versão atualizada armazenada no servidor.

---

# Implantação nas Demais Máquinas

Após a criação da imagem, os outros dois notebooks HP 240 G7 foram restaurados utilizando o Clonezilla.

Durante esse procedimento foi utilizada a imagem armazenada no pendrive de armazenamento.

Ao término da restauração, todas as máquinas passaram a possuir exatamente a mesma configuração da máquina modelo, incluindo:

* sistema operacional;
* drivers;
* programas instalados;
* configurações do Windows;
* otimizações realizadas;
* remoção de bloatware.

Isso garante que todos os computadores apresentem o mesmo comportamento e reduz problemas decorrentes de configurações diferentes.

---

# Procedimento de Restauração

Sempre que um notebook HP 240 G7 precisar ser restaurado, seguir o procedimento abaixo.

1. Conectar o pendrive do Clonezilla.
2. Conectar o pendrive de armazenamento contendo a imagem.
3. Inicializar o computador pelo pendrive do Clonezilla.
4. Selecionar a opção de restauração da imagem.
5. Escolher a imagem correspondente ao HP 240 G7.
6. Confirmar cuidadosamente o disco de destino.
7. Aguardar o término da restauração.
8. Reiniciar o computador.
9. Confirmar que o Windows inicializa normalmente.
10. Verificar o funcionamento dos drivers e dos programas instalados.

Caso a imagem esteja atualizada, nenhuma configuração adicional deverá ser necessária.

---

# Estado Atual do Projeto

Até o momento, o projeto encontra-se na seguinte situação:

* Estrutura de pendrives organizada.
* Máquina modelo configurada.
* Windows 10 padronizado.
* Aplicativos instalados utilizando Ninite.
* Drivers instalados utilizando DriverHub.
* Sistema otimizado utilizando Windows10Debloater.
* Imagem criada através do Clonezilla.
* Backup da imagem armazenado no servidor da escola.
* Três notebooks HP 240 G7 restaurados com sucesso utilizando a imagem criada.
* Processo de restauração validado.

---

# Próximos Passos

Esta documentação será expandida conforme o projeto evoluir.

Entre os próximos tópicos previstos estão:

* documentação do software de gerenciamento remoto;
* documentação de novos modelos de computadores;
* organização do inventário de equipamentos;
* manutenção das imagens do Clonezilla;
* procedimentos de atualização das imagens;
* organização dos backups;
* procedimentos de recuperação em caso de falhas;
* configuração da infraestrutura de rede para gerenciamento remoto.

---

# Observações

Sempre que uma imagem for modificada ou atualizada, esta documentação deve ser revisada para garantir que os procedimentos reflitam o estado atual do projeto.

O objetivo deste documento é garantir que qualquer integrante da equipe consiga compreender a estrutura do ambiente e realizar manutenções ou restaurações de forma segura, independentemente de quem tenha criado a imagem originalmente.
