# Caderno de laboratório — Etapa 1

## Identificação

- Projeto: Detecção e caracterização do micobioma micorrízico em transcriptomas públicos de orquídeas.

- Bolsista: Felipe Gomes da Silva

- Orientador: Rogerio Merces

- Período: \[01/10/26 — fim\]

- Repositório: \[endereço\]

- Cópia local: /home/felipe-gomes/Documentos/IC\_fungos\_orquideas

- Computador: \[identificação\]

## Escopo

Executar o fluxo completo nas seis bibliotecas indicadas em `data/metadata/`: conferir metadados, obter e verificar dados, executar FastQC e MultiQC dos dados brutos, processar com fastp, executar novo FastQC e MultiQC e interpretar os resultados.

Cada bolsista mantém seu próprio lablog. Dados brutos podem ser compartilhados na mesma máquina, mas execuções, logs, saídas e interpretações individuais devem ser identificados. As duas execuções não constituem novas réplicas biológicas.

## Como preencher

- Duplicar o bloco “Registro de sessão” a cada sessão de trabalho.

- Registrar comandos realmente executados, incluindo falhas e correções.

- Substituir os campos entre colchetes; marcar informações indisponíveis como NA e explicar.

- Usar caminhos relativos ao projeto sempre que possível.

- Referenciar logs e relatórios; não colar arquivos volumosos no caderno.

- Não registrar senhas, tokens, códigos de autorização ou conteúdo de arquivos de credenciais.

- Distinguir observação, interpretação e decisão aprovada.

- Preservar registros anteriores; documentar correções em novas entradas.

- Os blocos Bash abaixo são campos de registro, não scripts prontos de execução.

## Inventário inicial

Preencher com os identificadores reais. Se uma biblioteca tiver vários runs, acrescentar linhas.

| Biblioteca | Run | Layout | Espécie / tecido | Fonte dos metadados | Caminho dos FASTQ brutos | Observações |
| - | - | - | - | - | - | - |
| PRJNA348403 | SRR4431598 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | white\_part (parte branca) |
| PRJNA348403 | SRR4431599 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | green\_tip (ponta verde) |
| PRJNA815882 | SRR18319851 | NA | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | Tratamento NAA 20\_mg\_L |
| PRJNA815882 | SRR18319853 | NA | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | Controle (NAA\_0\_mg\_L) |
| PRJNA815882 | SRR18319854 | NA | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | Tratamento NAA\_5\_mg\_L |
| PRJNA815882 | SRR18319855 | NA | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | Tratamento NAA 10\_mg\_L |


## Referência do ambiente

Atualizar quando houver mudanças e registrar a data. As sessões devem indicar qual configuração utilizaram.

- Identificador da configuração: \[ex.: ambiente-v1\]

- Data: \[AAAA-MM-DD\]

- Sistema operacional: \[distribuição / versão\]

- CPU / RAM: \[informação\]

- Ambiente Conda/Mamba: \[nome\]

- Arquivo do ambiente: \[caminho\]

- Código: \[branch e hash do commit; indicar alterações locais não commitadas\]

- SRA Toolkit: \[versão\]

- FastQC: \[versão\]

- MultiQC: \[versão\]

- fastp: \[versão\]

- Compressão: \[ferramenta e versão\]

- Manifesto de checksums dos dados: \[caminho / algoritmo\]

## Progresso individual

Usar: pendente, em execução, concluído ou bloqueado. A conclusão deve apontar para registros e evidências.

| Biblioteca / run | Metadados | Dados verificados | QC bruto | fastp | QC após fastp | Interpretação | Revisão cruzada |
| - | - | - | - | - | - | - | - |
| PRJNA348403 / SRR4431598 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |
| PRJNA348403/ SRR4431599 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |
| PRJNA815882/SRR18319851 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |
| PRJNA815882/SRR18319853 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |
| PRJNA815882/SRR18319854 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |
| PRJNA815882/SRR18319855 | concluído | pendente | \[status\] | \[status\] | \[status\] | \[status\] | \[status\] |


## Registro de sessão — 2026-11-03 — Sessão 01

### 1. Identificação e objetivo

- Início / fim: 10:00 / 13:00 *(ajuste para o seu horário real)*

- Bolsista: Felipe Gomes da Silva

- Máquina: felipe-gomes-B850M-D3HP

- Diretório de trabalho: /home/felipe-gomes/Documentos/IC\_fungos\_orquideas

- Ambiente: base (para comandos do sistema) e ic\_bioinfo\_fungos (criado hoje)

- Branch / commit / alterações locais: main (sem alterações de código ainda)

- Tarefa ou issue: Atividade 1 (Metadados)

- Bibliotecas e runs: PRJNA348403 (SRR4431598, SRR4431599) e PRJNA815882 (SRR18319851, SRR18319853, SRR18319854, SRR18319855)

- Objetivo desta sessão: Completar a tabela de metadados buscando informações faltantes no SRA, verificar o espaço em disco,

- Etapa: metadados 


### 2. Entradas e pré-condições

| Entrada | Caminho ou identificador | Origem | Verificação / checksum | Observações |
| - | - | - | - | - |
| Tabela de amostras | data/metadata/samples\_template.tsv | Repositório | NA | Faltava layout, tamanho e réplicas |


- Espaço livre antes da execução: *(Coloque aqui o valor que apareceu no seu comando `df -h`, ex: 50 GB)*

- Recursos autorizados: NA (Apenas navegação web e instalação local)

- Dados brutos compartilhados ou próprios: Próprios (a serem baixados)

- Aprovação necessária para esta tarefa: não se aplica

### 3. Procedimento executado

Descrever as ações na ordem em que ocorreram, incluindo conferências manuais.

1. eitura do arquivo `samples\_template.tsv` para identificar as 6 bibliotecas.

2. Pesquisa no site NCBI SRA Run Selector pelos BioProjects PRJNA348403 e PRJNA815882 para descobrir o Layout (PAIRED/SINGLE) e o Tamanho dos arquivos.

3. Verificação do espaço em disco usando o comando `df -h`.

4. Correção do erro no `apt update` (remoção do repositório quebrado da Microsoft).

5. Criação do arquivo de ambiente `envs/qc\_trimming.yaml` e instalação do ambiente conda `ic\_bioinfo\_fungos`.

Comandos realmente executados:

```
\\\#`\# Verificação de espaço`

`df -h`

`\# Correção do apt`

`sudo nano /etc/apt/sources.list.d/algum-arquivo.list`

`sudo apt update`


`\# Criação do ambiente`

`mkdir -p envs`

`nano envs/qc\_trimming.yaml`

`conda env create -f envs/qc\_trimming.yaml`

`conda activate ic\_bioinfo\_fungos`

`\#\#/`
```

- Script utilizado: Nenhum`

- Arquivo de configuração: envs/qc\_trimming.yaml`

- Log de saída padrão: não registrado`

- Log de erros: não registrado`

- Status de saída: não registrado`

- Duração observada: aprox. 2 horas`


### 4. Parâmetros e justificativas 

Preencher quando houver fastp ou mudança de configuração. Não presumir que definir um limiar Q20 equivale a cortar todas as bases abaixo de Q20.

| Operação | Opção / valor efetivo | Padrão ou escolha explícita? | Justificativa / aprovação |
| - | - | - | - |
| Remoção de adaptadores | \[valor\] | \[informar\] | \[motivo\] |
| Corte por qualidade | \[valor ou desativado\] | \[informar\] | \[motivo\] |
| Filtragem por qualidade | \[valor\] | \[informar\] | \[motivo\] |
| Bases indefinidas | \[valor\] | \[informar\] | \[motivo\] |
| Comprimento mínimo | \[valor\] | \[informar\] | \[motivo\] |
| Tratamento de pares / órfãs | \[configuração e destino\] | \[informar\] | \[motivo\] |
| polyG / polyX e outros tratamentos | \[valor\] | \[informar\] | \[motivo\] |
| Threads | \[valor\] | \[informar\] | \[motivo\] |


- Protocolo aprovado: \[caminho / versão\]

- Exceção ao protocolo: \[nenhuma / descrição e autorização\]

### 5. Saídas e verificações

| Produto | Caminho | Tamanho / unidade | Verificação realizada | Resultado |
| - | - | - | - | - |
| Metadados preenchidos | Felipe\_lablog\_etapa1.md | No git | Inspeção visual | Tabela atualizada no log |


- Todos os arquivos esperados existem? sim 

- Dados brutos preservados? NA (download ainda não realizado)

- Pares conferidos, quando aplicável?  NA\]

- Relatórios incluem todos os arquivos previstos? NA\]

### 6. Observações de qualidade

Preencher apenas com resultados examinados nesta sessão. Para dados pareados, identificar R1 e R2 separadamente quando necessário.

| Biblioteca / run / mate | Evidência observada | Fonte do resultado | Interpretação provisória | Ação proposta |
| - | - | - | - | - |
| \[identificador\] | \[métrica / padrão / alerta\] | \[relatório e módulo\] | \[interpretação\] | \[ação\] |


Distinguir o que foi observado do que foi inferido. Não usar apenas a cor dos módulos como critério de aprovação ou exclusão.

### 7. Problemas, erros e correções

- Problema: O arquivo original `samples\_template.tsv` não continha informações sobre Layout, Réplicas Biológicas ou Tamanho dos arquivos. Erro no `apt update` bloqueando instalações no sistema.

- Mensagem exata, sem dados sensíveis: Erro: O repositório '[https://microsoft.com](https://microsoft.com/) stable Release' não tem um arquivo Release.

- Hipótese sobre a causa: Repositório de terceiros desatualizado no Ubuntu. Tabela de metadados do projeto fornecida incompleta de propósito para exercício de consolidação.

- Alteração realizada: O link com erro foi comentado no arquivo correspondente em `/etc/apt/sources.list.d/`. O layout e os tamanhos foram resgatados consultando diretamente o NCBI SRA Run Selector.

- Reexecução: `sudo apt update`

- Resultado após correção: `apt update` concluído com sucesso. Tabela de metadados consolidada.

- Pendência: nenhuma

### 8. Fechamento da sessão

- Objetivo alcançado? sim

- Resultado principal: Tabela de metadados totalmente preenchida com layout PAIRED/NA e estimativa de tamanho.

- Arquivos alterados: `Felipe\_lablog\_etapa1.md`

- Revisão solicitada a:

- Próxima ação: Iniciar a Atividade 2 (Criação do Ambiente)

- Decisão dependente do orientador: Aprovação da tabela de metadados finalizada.

## Comparação antes/depois — preencher ao concluir o processamento

Criar linhas adicionais por run e, quando necessário, por mate. Identificar se as métricas se referem a um arquivo, ao par ou à biblioteca agregada.

| Biblioteca / run | Unidade contada | Entrada | Retida | Retenção (%) | Fonte das contagens | Comprimento antes/depois | Síntese do efeito do fastp |
| - | - | - | - | - | - | - | - |
| \[biblioteca 1\] | \[leituras / pares\] | \[valor\] | \[valor\] | \[valor\] | \[JSON / relatório\] | \[métrica e valores\] | \[síntese\] |
| \[biblioteca 2\] | \[unidade\] | \[valor\] | \[valor\] | \[valor\] | \[fonte\] | \[valores\] | \[síntese\] |
| \[biblioteca 3\] | \[unidade\] | \[valor\] | \[valor\] | \[valor\] | \[fonte\] | \[valores\] | \[síntese\] |
| \[biblioteca 4\] | \[unidade\] | \[valor\] | \[valor\] | \[valor\] | \[fonte\] | \[valores\] | \[síntese\] |
| \[biblioteca 5\] | \[unidade\] | \[valor\] | \[valor\] | \[valor\] | \[fonte\] | \[valores\] | \[síntese\] |
| \[biblioteca 6\] | \[unidade\] | \[valor\] | \[valor\] | \[valor\] | \[fonte\] | \[valores\] | \[síntese\] |


Retenção (%) = 100 × quantidade retida / quantidade de entrada.

Usar a mesma unidade no numerador e denominador. Registrar separadamente eventuais leituras órfãs para evitar ambiguidades.

### Diagnóstico final por biblioteca

Duplicar para cada biblioteca.

- Biblioteca / runs: \[identificadores\]

- Problemas iniciais: \[descrição\]

- Evidências de melhora: \[métricas e relatórios\]

- Problemas persistentes: \[descrição ou nenhum\]

- Perda de dados e avaliação: \[descrição\]

- Recomendação: \[prosseguir / investigar / reprocessar\]

- Justificativa: \[evidências\]

- Decisão do orientador: \[pendente / decisão, data e registro\]

## Revisão cruzada e comparação das execuções

Duplicar este bloco a cada revisão.

- Data: \[AAAA-MM-DD\]

- Autor da execução: \[nome\]

- Revisor: \[nome\]

- Bibliotecas / runs revisados: \[lista\]

- Arquivos e registros examinados: \[caminhos\]

| Item | Resultado | Evidência / correção necessária |
| - | - | - |
| Entradas e checksums correspondem | \[sim / não / pendente\] | \[evidência\] |
| Versões e parâmetros conferidos | \[resultado\] | \[evidência\] |
| Logs e saídas completos | \[resultado\] | \[evidência\] |
| Contagens e retenção conferidas | \[resultado\] | \[evidência\] |
| Interpretação sustentada pelos relatórios | \[resultado\] | \[evidência\] |
| Procedimento reproduzível a partir dos registros | \[resultado\] | \[evidência\] |


- Divergências entre bolsistas: \[descrição ou nenhuma\]

- Investigação realizada: \[ações e resultados\]

- Correções solicitadas: \[lista\]

- Registro de resolução: \[sessão / issue\]

- Situação: \[aprovado / aprovado com pendências / revisar\]

## Registro de decisões com o orientador

| Data | Assunto | Evidências apresentadas | Decisão | Responsável / prazo | Registro relacionado |
| - | - | - | - | - | - |
| \[data\] | \[assunto\] | \[relatórios\] | \[decisão ou pendente\] | \[responsável e prazo\] | \[sessão / issue\] |


## Encerramento individual da Etapa 1

- [ ] 

- Metadados das seis bibliotecas conferidos.

- [x] 

- Todos os runs contabilizados.

- [x] 

- Dados utilizados verificados e identificados.

- [ ] 

- FastQC e MultiQC brutos executados para o conjunto completo.

- [ ] 

- Protocolo do fastp aprovado e registrado.

- [ ] 

- fastp executado nas seis bibliotecas.

- [ ] 

- FastQC e MultiQC após processamento executados para o conjunto completo.

- [ ] 

- Comparações antes/depois concluídas.

- [ ] 

- Resultados comparados com os do colega.

- [ ] 

- Revisão cruzada registrada.

- [ ] 

- Relatório individual concluído.

- [ ] 

- Pendências apresentadas ao orientador.

- Relatório individual: \[caminho\]

- Síntese conjunta: \[caminho\]

- Pendências finais: \[lista ou nenhuma\]

- Avaliação do orientador: \[pendente / decisão\]

- Data do encerramento: \[AAAA-MM-DD\]

A próxima etapa depende de aprovação do orientador. Não registrar etapas ainda planejadas como concluídas.

