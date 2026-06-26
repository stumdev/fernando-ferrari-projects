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
* [Observações](#observações)
* [Créditos](#créditos)

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

Cada pendrive possui uma finalidade específica e deve permanecer organizado para evitar erros durante o processo de instalação ou restauração.

---

# Ambiente Atual

Até o momento, o procedimento foi aplicado em três notebooks do seguinte modelo:

**HP 240 G7**

Todos os equipamentos possuem a mesma configuração de hardware, permitindo utilizar uma única imagem para restaurar qualquer máquina desse modelo.

Caso novos computadores com hardware diferente sejam incorporados ao projeto, será necessário criar uma imagem específica para cada novo modelo.

---

# Preparação da Máquina Modelo

Foi escolhido um notebook HP 240 G7 para servir como máquina de referência.

Todo o procedimento descrito abaixo foi executado apenas nessa máquina.

## 1. Instalação do sistema operacional

Foi realizada uma instalação limpa do Windows 10 utilizando um dos pendrives de instalação disponíveis.

---

## 2. Configuração inicial

Após a instalação do Windows, foram realizadas as configurações iniciais necessárias para utilização da máquina.

Atualmente o equipamento permanece sem senha de acesso, facilitando o processo de implantação.

---

## 3. Instalação dos programas

Os softwares utilizados pela escola foram instalados utilizando o Ninite.

Essa ferramenta permite instalar diversos programas automaticamente, reduzindo o tempo necessário para preparação da máquina.

---

## 4. Instalação dos drivers

Após a instalação dos programas, todos os drivers foram instalados utilizando o DriverHub.

Antes de prosseguir, foi verificado que nenhum dispositivo permanecia com drivers pendentes.

---

## 5. Limpeza e otimização

Após confirmar que o sistema estava totalmente funcional, foi executado o Windows10Debloater.

Essa ferramenta remove aplicativos desnecessários instalados juntamente com o Windows (bloatware), reduz processos em segundo plano e melhora o desempenho geral do sistema.

Essa etapa deve ser realizada apenas após confirmar que todos os drivers e programas necessários estão funcionando corretamente.

---

# Criação da Imagem

Após concluir toda a configuração da máquina modelo, foi utilizado o Clonezilla para criar uma imagem completa do disco.

Essa imagem foi armazenada no pendrive destinado exclusivamente ao armazenamento das imagens.

A partir desse momento, essa imagem passa a ser considerada a instalação padrão para notebooks HP 240 G7.

Sempre que forem realizadas alterações importantes na configuração da máquina modelo, recomenda-se gerar uma nova imagem para manter o padrão atualizado.

---

# Backup das Imagens

Como medida de segurança, todas as imagens armazenadas no pendrive de armazenamento também possuem uma cópia de segurança no servidor da escola.

Caso o pendrive de armazenamento seja perdido, danificado ou apresente qualquer tipo de falha, **não será necessário recriar toda a imagem**, desde que a cópia existente no servidor permaneça íntegra.

Nessa situação, a imagem poderá ser recuperada diretamente pela rede e copiada novamente para um pendrive de armazenamento ou utilizada conforme a infraestrutura disponível.

Antes de iniciar qualquer processo de criação de uma nova imagem, sempre verifique se já existe uma versão atualizada armazenada no servidor.

---

# Implantação nas Demais Máquinas

Após a criação da imagem, os outros dois notebooks HP 240 G7 foram restaurados utilizando o Clonezilla.

Durante esse procedimento foi utilizada a imagem armazenada no pendrive de armazenamento.

Ao término da restauração, todas as máquinas passaram a possuir exatamente a mesma configuração da máquina modelo, incluindo:

* sistema operacional;
* drivers instalados;
* programas instalados;
* configurações do Windows;
* otimizações realizadas;
* remoção de aplicativos desnecessários.

Esse procedimento garante que todos os computadores permaneçam padronizados e reduz significativamente o tempo necessário para preparar novas máquinas.

---

# Procedimento de Restauração

Sempre que um notebook HP 240 G7 precisar ser restaurado, seguir o procedimento abaixo.

1. Conectar o pendrive do Clonezilla.
2. Conectar o pendrive de armazenamento contendo a imagem.
3. Inicializar o computador utilizando o pendrive do Clonezilla.
4. Selecionar a opção de restauração da imagem.
5. Escolher a imagem correspondente ao HP 240 G7.
6. Confirmar cuidadosamente o disco de destino para evitar sobrescrever outro dispositivo.
7. Iniciar o processo de restauração.
8. Aguardar a conclusão do procedimento.
9. Reiniciar o computador.
10. Confirmar que o Windows inicia normalmente.
11. Verificar se todos os drivers e programas estão funcionando corretamente.

Caso a imagem esteja atualizada, nenhuma configuração adicional deverá ser necessária.

---

# Estado Atual do Projeto

Atualmente o projeto encontra-se na seguinte situação:

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

Os próximos tópicos previstos incluem:

* documentação do software de gerenciamento remoto;
* documentação de novos modelos de computadores;
* organização do inventário de equipamentos;
* manutenção das imagens do Clonezilla;
* atualização periódica das imagens padrão;
* procedimentos de recuperação em caso de falhas;
* documentação da infraestrutura de rede;
* procedimentos para atualização e manutenção do software de gerenciamento remoto.

---

# Observações

Sempre que uma imagem for modificada ou atualizada, esta documentação deverá ser revisada para refletir corretamente o estado atual do projeto.

O objetivo deste documento é garantir que qualquer integrante consiga compreender toda a estrutura do ambiente e realizar manutenções ou restaurações de forma segura e padronizada.

---

# Créditos

## Documentação

Esta documentação foi elaborada por:

* **Bruno Pereira Stum**

Responsável pela organização, manutenção e atualização desta documentação técnica.

## Equipe do Projeto

A preparação das máquinas, formatação, padronização dos computadores, criação das imagens, testes e implantação da infraestrutura foram realizadas pelos alunos:

* **Bruno Pereira Stum**
* **João Henrique Pinheiro Daudt**
* **Lorenzo Nedel Mello**

O projeto foi desenvolvido como parte das atividades de infraestrutura e gerenciamento de computadores da Escola Estadual de Ensino Médio Fernando Ferrari.

Este documento deverá ser atualizado sempre que novos procedimentos, equipamentos ou funcionalidades forem adicionados ao projeto, garantindo que futuras equipes possam dar continuidade ao trabalho sem perda de informações.
