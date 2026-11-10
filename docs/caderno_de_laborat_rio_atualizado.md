# Caderno de laboratório — Etapa 1

## Identificação

- Projeto: Detecção e caracterização do micobioma micorrízico em transcriptomas públicos de orquídeas.

- Bolsista: Felipe Gomes da Silva

- Orientador: Rogerio Merces

- Período: \[01/10/26 — 2027\]

- Repositório: [https://github.com/FelipeUefs/IC\_fungos\_orquideas](https://github.com/FelipeUefs/IC_fungos_orquideas)

- Cópia local: /home/felipe-gomes/Documentos/IC\_fungos\_orquideas

- Computador: felipe-gomes-B850M-D3HP

## Escopo

Executar o fluxo completo nas seis bibliotecas indicadas em `data/metadata/`: conferir metadados, obter e verificar dados, executar FastQC e MultiQC dos dados brutos, processar com fastp, executar novo FastQC e MultiQC e interpretar os resultados.

Cada bolsista mantém seu próprio lablog. Dados brutos podem ser compartilhados na mesma máquina, mas execuções, logs, saídas e interpretações individuais devem ser identificados. As duas execuções não constituem novas réplicas biológicas.

## Inventário inicial

Preencher com os identificadores reais. Se uma biblioteca tiver vários runs, acrescentar linhas.

| Biblioteca | Run | Layout | Espécie / tecido | Fonte dos metadados | Caminho dos FASTQ brutos | Tamanho | Observações |
| - | - | - | - | - | - | - | - |
| PRJNA348403 | SRR4431598 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 3.02 Gb | white\_part (parte branca) |
| PRJNA348403 | SRR4431599 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 2.88 Gb | green\_tip (ponta verde) |
| PRJNA815882 | SRR18319851 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 6.3 Gb | Tratamento NAA 20\_mg\_L |
| PRJNA815882 | SRR18319853 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 5.7 Gb | Controle (NAA\_0\_mg\_L) |
| PRJNA815882 | SRR18319854 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 6.5 Gb | Tratamento NAA\_5\_mg\_L |
| PRJNA815882 | SRR18319855 | PAIRED | D. catenatum | samples\_template.tsv / NCBI | data/raw/ | 6.2 Gb | Tratamento NAA 10\_mg\_L |


## Referência do ambiente

- Identificador da configuração: ambiente-v1

- Data: 2026-11-09

- Sistema operacional: Ubuntu 24.04 (Linux 7.0.0-38-generic)

- CPU / RAM: AMD Ryzen 7 7700X / 32 GB DDR5

- Ambiente Conda/Mamba: ic\_bioinfo\_fungos

- Arquivo do ambiente: envs/pipeline\_env.yml

- Código: main (sem alterações locais)

- SRA Toolkit: \>=3.0.0

- FastQC: \>=0.12.1

- MultiQC: \>=1.19

- fastp: \[versão\]

- Compressão: pigz

- Manifesto de checksums dos dados: NA

## Progresso individual

| Biblioteca / run | Metadados | Dados verificados | QC bruto | fastp | QC após fastp | Interpretação | Revisão cruzada |
| - | - | - | - | - | - | - | - |
| PRJNA348403 / SRR4431598 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |
| PRJNA348403/ SRR4431599 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |
| PRJNA815882/SRR18319851 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |
| PRJNA815882/SRR18319853 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |
| PRJNA815882/SRR18319854 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |
| PRJNA815882/SRR18319855 | concluído | concluído | pendente | pendente | pendente | pendente | pendente |


## Registro de sessão — 2026-11-03 — Sessão 01

### 1. Identificação e objetivo

- Início / fim: 10:00 / 12:30

- Bolsista: Felipe Gomes da Silva

- Máquina: felipe-gomes-B850M-D3HP

- Diretório de trabalho: /home/felipe-gomes/Documentos/IC\_fungos\_orquideas

- Ambiente: base (para comandos do sistema)

- Tarefa ou issue: Atividade 1 (Metadados)

- Bibliotecas e runs: PRJNA348403 (SRR4431598, SRR4431599) e PRJNA815882 (SRR18319851, SRR18319853, SRR18319854, SRR18319855)

- Objetivo desta sessão: Completar a tabela de metadados buscando informações faltantes no SRA e verificar o espaço em disco.

- Etapa: Metadados

### 2. Entradas e pré-condições

| Entrada | Caminho ou identificador | Origem | Verificação / checksum | Observações |
| - | - | - | - | - |
| Tabela de amostras | data/metadata/samples\_template.tsv | Repositório | NA | Faltava layout, tamanho e réplicas |


- Espaço livre antes da execução: 837 GB no SSD NVME

- Recursos autorizados: NA (Apenas navegação web e comandos de sistema)

- Dados brutos compartilhados ou próprios: Próprios (a serem baixados)

- Aprovação necessária para esta tarefa: não se aplica

### 3. Procedimento executado

1. Leitura do arquivo `samples\_template.tsv` para identificar as 6 bibliotecas.

2. Pesquisa no site NCBI SRA Run Selector pelos BioProjects PRJNA348403 e PRJNA815882 para descobrir o Layout (PAIRED) e o Tamanho dos arquivos.

3. Verificação do espaço em disco usando o comando `df -h`.

Comandos realmente executados:

```
\# Verificação de espaço    
df -h  
```

- Script utilizado: Nenhum

- Arquivo de configuração: Nenhum

- Log de saída padrão: não registrado

- Log de erros: não registrado

- Status de saída: não registrado

- Duração observada: aprox. 2h30 horas

### 4. Parâmetros e justificativas

| Operação | Opção / valor efetivo | Padrão ou escolha explícita? | Justificativa / aprovação |
| - | - | - | - |
| NA | NA | NA | O fastp não foi executado nesta sessão |


- Protocolo aprovado: NA

- Exceção ao protocolo: nenhuma

### 5. Saídas e verificações

| Produto | Caminho | Tamanho / unidade | Verificação realizada | Resultado |
| - | - | - | - | - |
| Metadados preenchidos | Felipe\_lablog\_etapa1.md | No git | Inspeção visual | Tabela atualizada no log |


- Todos os arquivos esperados existem? sim

- Dados brutos preservados? NA (download ainda não realizado)

- Pares conferidos, quando aplicável? NA

- Relatórios incluem todos os arquivos previstos? NA

### 6. Observações de qualidade

| Biblioteca / run / mate | Evidência observada | Fonte do resultado | Interpretação provisória | Ação proposta |
| - | - | - | - | - |
| NA | NA | NA | Análise será feita na Atividade 4 | NA |


### 7. Problemas, erros e correções

- Problema: O arquivo original `samples\_template.tsv` não continha informações sobre Layout, Réplicas Biológicas ou Tamanho dos arquivos.

- Hipótese sobre a causa: Tabela de metadados do projeto fornecida incompleta de propósito para exercício de consolidação.

- Alteração realizada: O layout (PAIRED) e os tamanhos (total de 30.6 Gb) foram resgatados consultando diretamente o NCBI SRA Run Selector. A informação de réplicas biológicas foi preenchida como NA por não estar explícita, conforme a orientação do projeto de não inventar dados.

- Pendência: nenhuma

### 8. Fechamento da sessão

- Objetivo alcançado? sim

- Resultado principal: Tabela de metadados totalmente preenchida com layout PAIRED e estimativa de tamanho (total ~30.6 Gb).

- Arquivos alterados: `Felipe\_lablog\_etapa1.md`

- Revisão solicitada a: Orientador

- Próxima ação: Iniciar a Atividade 2 (Configuração de Ambiente) e Atividade 3 (Obtenção de dados).

- Decisão dependente do orientador: Aprovação da tabela de metadados finalizada.

## Registro de sessão — 2026-11-09 — Sessão 02

### 1. Identificação e objetivo

- **Bolsista:** Felipe Gomes da Silva

- **Máquina:** felipe-gomes-B850M-D3HP

- **Diretório de trabalho:** `/home/felipe-gomes/Documentos/IC\_fungos\_orquideas`

- **Ambiente:** base e `ic\_bioinfo\_fungos`

- **Tarefa:** Atividade 2 (Criação de Ambiente) e Atividade 3 (Obtenção e verificação dos dados)

- **Objetivo:** Configurar o ambiente virtual Conda com as ferramentas do projeto, obter os seis runs públicos, convertê-los para FASTQ pareado e documentar as verificações necessárias.

- **Runs:** SRR4431598, SRR4431599, SRR18319851, SRR18319853, SRR18319854, SRR18319855.

### 2. Entradas e pré-condições

| Entrada | Origem / caminho | Observação |
| - | - | - |
| Identificadores e layout PAIRED | `data/metadata/samples\_template.tsv` e inventário do lablog | Metadados consolidados na Atividade 1 |
| Rede | Proxy institucional da UEFS | Proxy utilizado: `10.65.16.35:3128` |


### 3. Procedimento executado e evidências

1. Correção do erro no `apt update` (remoção do repositório quebrado da Microsoft que impedia atualizações).

2. Leitura e execução do arquivo de ambiente `envs/pipeline\_env.yml` contendo dependências como `sra-tools`, `fastqc`, `pigz` e ferramentas do pipeline.

3. Instalação e ativação do ambiente conda `ic\_bioinfo\_fungos` para isolamento de pacotes.

4. Identificada a utilização de proxy institucional da UEFS para solucionar problemas de conexão (`Failed to call external services`).

5. Conversão de todos os 6 runs efetuada utilizando um laço `for` com a ferramenta `fasterq-dump`.

6. Os dados foram extraídos com sucesso na pasta `data/raw`, gerando exatos 12 arquivos FASTQ (já que todas as 6 bibliotecas possuem layout PAIRED, resultando em leituras \_1 e \_2 para cada).

7. Procedeu-se à compressão paralela dos arquivos brutos para formato `.fastq.gz` visando economia de espaço em disco e melhoria de desempenho.

**Comandos relevantes registrados na sessão:**

```
\# Correção do apt e repositórios  
sudo rm /etc/apt/sources.list.d/vscode.list    
sudo apt update    
  
\# Criação e ativação do ambiente  
conda env create -f envs/pipeline\_env.yml    
conda activate ic\_bioinfo\_fungos  
  
\# Acesso ao diretório de trabalho  
cd data/raw  
  
\# Obtenção dos dados após configuração de proxy  
for run in SRR4431598 SRR4431599 SRR18319851 SRR18319853 SRR18319854 SRR18319855; do  
    fasterq-dump --split-files --progress "$run"  
done  
  
\# Compressão dos 12 arquivos FASTQ gerados  
pigz -p 4 \*.fastq
```

### 4. Parâmetros e justificativas

| Operação | Parâmetro | Finalidade |
| - | - | - |
| `fasterq-dump` | `--split-files` | Produzir arquivos separados para R1 e R2 em dados pareados |
| `fasterq-dump` | `--progress` | Acompanhar o andamento da conversão |
| `pigz` | `-p 4` | Utilizar quatro threads para acelerar a compressão dos arquivos FASTQ sem perda de dados |


### 5. Saídas e verificações

| Produto / Run | Evidência disponível | Estado documentado |
| - | - | - |
| Ambiente Conda | `envs/pipeline\_env.yml` | Sucesso na ativação |
| SRR4431598 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |
| SRR4431599 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |
| SRR18319851 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |
| SRR18319853 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |
| SRR18319854 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |
| SRR18319855 | FASTQ R1 e R2 (.gz) | Extração e compressão concluídas |


- \[x\] Criação do ambiente virtual com as dependências do projeto.

- \[x\] Confirmar os 12 arquivos FASTQ esperados.

- \[x\] Compressão dos dados brutos com `pigz`.

- \[x\] Registrar checksums SHA-256 das entradas utilizadas.

### 6. Observações de qualidade

A avaliação de qualidade por base, adaptadores e conteúdo GC está prevista para a Atividade 4 (FastQC/MultiQC).

### 7. Problemas, erros e correções

| Problema | Evidência | Tratamento / situação |
| - | - | - |
| Atualização de sistema bloqueada | `Erro: O repositório 'https://microsoft.com stable Release' não tem um arquivo Release` | O link com erro foi apagado no arquivo correspondente em `/etc/apt/sources.list.d/`. `apt update` executado com sucesso. |
| Conflito de pacotes no terminal | Inicialização padrão no ambiente `(base)` do Miniforge | Utilizado o comando `conda activate ic\_bioinfo\_fungos` para garantir o isolamento das ferramentas do projeto. |
| Falha no acesso a serviços externos | `Failed to call external services` | Configuração de proxy institucional; download procedeu normalmente após correção |


### 8. Fechamento da sessão

- **Objetivo das Atividades 2 e 3 integralmente alcançado?** Sim. O ambiente virtual foi configurado, todos os 6 runs foram baixados, extraídos em 12 arquivos FASTQ e o processo de compressão paralela foi concluído.

- **Resultado principal confirmado:** Ambiente ativo e arquivos `.fastq.gz` disponíveis em `data/raw/`.

- **Pendências:** Conferir os checksums e comparar resultados.

- **Próxima ação:** Iniciar a Atividade 4 (FastQC e MultiQC dos dados brutos).

## Registro de sessão — 2026-11-10 — Sessão 03

### 1. Identificação e objetivo

- **Bolsista:** Felipe Gomes da Silva

- **Máquina:** felipe-gomes-B850M-D3HP

- **Diretório de trabalho:** `/home/felipe-gomes/Documentos/IC\_fungos\_orquideas`

- **Ambiente:** `ic\_bioinfo\_fungos`

- **Tarefa:** Atividade 3 — Verificação dos dados brutos após compactação.

- **Objetivo:** Confirmar integridade gzip, registrar e validar checksums SHA-256 e comparar as contagens de leituras entre R1 e R2 dos seis runs.

### 2. Entradas e pré-condições

- **Entradas:** 12 arquivos `\*.fastq.gz` em `data/raw/`, referentes a seis runs paired-end.

- **Origem:** FASTQ convertidos dos dados SRA e compactados com `pigz -p 4` na sessão anterior.

- **Manifesto de integridade:** `data/metadata/checksums\_sha256.txt`.

### 3. Procedimento executado

**3.1. Verificação de integridade gzip**

A partir da pasta `data/raw/`, foi executado:

```
`pigz -t \*.fastq.gz`

`echo $?`
```

**Resultado observado:** código de saída `0`, sem erros reportados.

**3.2. Geração e validação dos checksums SHA-256**

A partir da pasta principal do projeto:

```
`mkdir -p data/metadata`

`sha256sum data/raw/\*.fastq.gz \> data/metadata/checksums\_sha256.txt`

`sha256sum -c data/metadata/checksums\_sha256.txt`
```

**Resultado observado:** 12 entradas SHA-256; na conferência, os 12 arquivos retornaram `OK`.

**3.3. Conferência da quantidade de leituras R1/R2**

A partir da pasta `data/raw/`, a contagem de linhas foi obtida por descompressão em fluxo e `wc -l`, com quatro linhas por leitura:

```
`for r1 in \*\_1.fastq.gz; do`

`    r2="$\{r1/\_1.fastq.gz/\_2.fastq.gz\}"`

`    n1=$(pigz -dc "$r1" | wc -l)`

`    n2=$(pigz -dc "$r2" | wc -l)`

`    if (( n1 == n2 && n1 % 4 == 0 )); then`

`        echo "OK: $r1 e $r2 possuem $((n1 / 4)) leituras cada."`

`    else`

`        echo "ATENÇÃO: verificar $r1 e $r2"`

`    fi`

`done`


### 4. Parâmetros e justificativas

| **Operação** | **Parâmetro / método** | **Finalidade** |
| :-: | :-: | :-: |
| Integridade gzip | `pigz -t` | Detectar erros de integridade na descompressão gzip. |
| Identificação de arquivos | `sha256sum` (SHA-256) | Registrar impressões digitais dos arquivos compactados. |
| Conferência do manifesto | `sha256sum -c` | Comparar os arquivos atuais aos hashes registrados. |
| Contagem de leituras | `pigz -dc`, `wc -l`, divisão por 4 | Conferir contagens e compatibilidade do número de linhas com FASTQ. |


### 5. Saídas e verificações

| **Run** | Leituras R1 | Leituras R2 | **Resultado da contagem** |
| :-: | -: | -: | :-: |
| SRR18319851 | 70.736.989 | 70.736.989 | OK |
| SRR18319853 | 63.518.044 | 63.518.044 | OK |
| SRR18319854 | 71.470.881 | 71.470.881 | OK |
| SRR18319855 | 69.569.135 | 69.569.135 | OK |
| SRR4431598 | 25.170.441 | 25.170.441 | OK |
| SRR4431599 | 24.021.467 | 24.021.467 | OK |
| **Total** | **324.486.957** | **324.486.957** | **6 pares com contagens iguais** |


**Integridade gzip:** 12 arquivos testados, comando encerrado com status `0`.

**Checksums SHA-256:** 12 hashes gerados e 12 arquivos validados com `OK`.

**Contagens R1/R2:** 324.486.957 pares de leituras contabilizados, totalizando 648.973.914 leituras individuais.

**Arquivo de evidência:** `data/metadata/checksums\_sha256.txt`.

### 6. Observações de qualidade

A igualdade de contagens e o número de linhas múltiplo de quatro **não comprovam**, isoladamente, a estrutura completa de cada registro FASTQ nem a correspondência dos identificadores de leitura entre R1 e R2. O teste gzip confirma a integridade da codificação compactada, enquanto o SHA-256 confirma a correspondência com o manifesto gerado, não com um arquivo de referência externo.

A análise de qualidade das sequências (qualidade por base, adaptadores, GC etc.) será feita na Atividade 4 (FastQC/MultiQC).

### 7. Problemas, erros e correções

- **Tentativa inicial:** `pigz -t \*.fastq.gz` foi executado na raiz do projeto e retornou `pigz: skipping: \*.fastq.gz does not exist`, porque os arquivos estavam em `data/raw/`.

- **Correção:** execução do teste dentro de `data/raw/`, com retorno `0`.

- **Outras divergências:** nenhuma relatada na validação SHA-256 ou na comparação das contagens.

### 8. Fechamento da sessão

- **Objetivo desta sessão alcançado?** Sim, para integridade gzip, validação SHA-256 e compatibilidade das contagens entre os pares.

- **Resultado principal:** os 12 arquivos passaram no teste gzip e na validação de checksums; os seis pares apresentaram contagens R1/R2 iguais.

- **Próxima ação:** Iniciar a Atividade 4 (FastQC/MultiQC dos dados brutos).

## Encerramento individual da Etapa 1

- \[x\] Metadados das seis bibliotecas conferidos.

- \[x\] Todos os runs contabilizados.

- \[x\] Dados utilizados verificados e identificados.

- \[ \] FastQC e MultiQC brutos executados para o conjunto completo.

- \[ \] Protocolo do fastp aprovado e registrado.

- \[ \] fastp executado nas seis bibliotecas.

- \[ \] FastQC e MultiQC após processamento executados para o conjunto completo.

- \[ \] Comparações antes/depois concluídas.

- \[ \] Resultados comparados com os do colega.

- \[ \] Revisão cruzada registrada.

- \[ \] Relatório individual concluído.

- \[ \] Pendências apresentadas ao orientador.

- Data do encerramento: NA

