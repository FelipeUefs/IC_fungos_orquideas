# Plano de ação dos bolsistas — Etapa 1

## Projeto

Detecção e caracterização do micobioma micorrízico em transcriptomas públicos de orquídeas.

- Laboratório: BIOINFO-UEFS.

- Orientacao: Prof. Rogerio Merces Ferreira Santos

- Colaboração: UESC — Prof. Dr. Eric Roberto Guimarães Rocha Aguiar.

- Escopo: consolidação do projeto, obtenção dos dados, controle de qualidade inicial, processamento com fastp, novo controle de qualidade e interpretação dos resultados.

- Dados: as seis bibliotecas já indicadas em `data/metadata/`.

## 1. Objetivo

Capacitar os dois integrantes para executar e compreender o fluxo completo de aquisição e pré-processamento das seis bibliotecas, produzindo resultados rastreáveis, revisados e comparáveis. usar GIT.

Cada integrante executará as seis bibliotecas. Ambos terão as mesmas atividades, entregas e critérios de conclusão.

Esta etapa não inclui remoção do hospedeiro, classificação taxonômica, anotação de domínios ou análises de diversidade.

## 2. Fluxo de trabalho

```
Consolidação do projeto e conferência dos metadados  
    ↓  
Preparação do ambiente e planejamento de recursos  
    ↓  
Download, conversão e verificação dos dados  
    ↓  
FastQC dos dados brutos  
    ↓  
MultiQC dos dados brutos  
   
Trimagem 1- Processamento com fastp (parametros padrao pesquisar)  
    ↓  
Processamento das seis bibliotecas com fastp  
    ↓  
FastQC dos dados processados  
    ↓  
MultiQC dos dados processados  
    ↓  
Comparação antes/depois e fechamento do lablog 
```

## 3. Responsabilidades equivalentes

| Atividade | Felipe | Stela |
| - | - | - |
| Conferência dos metadados | Todas as seis bibliotecas | Todas as seis bibliotecas |
| Capacitação em obtenção dos dados | Executar e documentar o procedimento | Executar e documentar o procedimento |
| Verificação dos arquivos | Todas as seis bibliotecas | Todas as seis bibliotecas |
| FastQC dos dados brutos | Todas as seis bibliotecas | Todas as seis bibliotecas |
| MultiQC inicial | Consolidar seu conjunto completo | Consolidar seu conjunto completo |
| Proposta de parâmetros | Elaborar e discutir | Elaborar e discutir |
| fastp | Todas as seis bibliotecas | Todas as seis bibliotecas |
| FastQC após processamento | Todas as seis bibliotecas | Todas as seis bibliotecas |
| MultiQC após processamento | Consolidar seu conjunto completo | Consolidar seu conjunto completo |
| Comparação antes/depois | Analisar todas as seis bibliotecas | Analisar todas as seis bibliotecas |
| Apresentação do lablog | Entrega individual | Entrega individual |


### Execuções independentes sem desperdício de armazenamento

- Cada integrante utilizará sua própria cópia de trabalho, scripts, logs e resultados em pastas separadas, sem sobrescrever arquivos do colega.

- Cada um poderá obter e verificar sua própria cópia dos dados.

- Execuções pesadas na mesma máquina serão agendadas para evitar disputa por CPU, memória e disco.

## 4. Organização proposta

A estrutura abaixo deve ser adaptada ao conteúdo já existente, sem sobrescrever arquivos. Em cópias separadas do repositório, cada estudante poderá manter apenas seus próprios diretórios de resultados.

```
data/  
├── metadata/  
├── sra/  
├── raw/  
└── processed/  
    ├── bolsista\_a/fastp/  
    └── bolsista\_b/fastp/  
envs/  
└── qc.yml  
scripts/  
├── download/  
└── qc/  
logs/  
├── bolsista\_a/  
└── bolsista\_b/  
results/qc/  
├── bolsista\_a/  
│   ├── fastqc\_raw/  
│   ├── multiqc\_raw/  
│   ├── fastp/  
│   ├── fastqc\_processed/  
│   └── multiqc\_processed/  
└── bolsista\_b/  
    ├── fastqc\_raw/  
    ├── multiqc\_raw/  
    ├── fastp/  
    ├── fastqc\_processed/  
    └── multiqc\_processed/  
docs/  
├── protocolo\_etapa1.md  
├── lablog\_bolsista\_a.md  
├── lablog\_bolsista\_b.md  
├── relatorio\_etapa1\_bolsista\_a.qmd  
├── relatorio\_etapa1\_bolsista\_b.qmd  
└── comparacao\_execucoes\_etapa1.md
```

## 5. Atividade 1 — Consolidação e metadados

### Checklist individual

- [x] Ler README.md, materiais e artigos referencias do projeto

- [x] Examinar os arquivos existentes em data/metadata/.

- [x] Identificar as seis bibliotecas e todos os runs associados.

- [x] Distinguir biblioteca, run e réplica biológica.

- [x] Conferir espécie, tecido, condição, layout e replicação, quando disponíveis.

- [x] Registrar lacunas sem inventar informações.

- [x] Estimar o volume de dados e verificar espaço disponível.

- [x] Registrar decisões com o orientador.

Registrar informações ausentes como NA, com explicação em notes. Se uma biblioteca tiver vários runs, registrar todos e não concatená-los automaticamente.

### Aceite

As seis bibliotecas e seus runs estão contabilizados; divergências foram resolvidas ou documentadas; ambos conseguem explicar a organização dos dados.

## 6. Atividade 2 — Ambiente e recursos

### Ferramentas

SRA Toolkit, FastQC, MultiQC, fastp, ferramenta de compressão e Git.

### Checklist individual

- [ ] Inspecionar os ambientes e scripts existentes antes de alterá-los.

- [ ] Preparar ou ativar o ambiente de aquisição e QC.

- [ ] Registrar versões e comandos de execução - criar arquivo qc\_trimming.yaml para o ambiente e colocar em /envs

- [ ] Conferir diretórios de entrada, saída e temporários.

- [ ] Combinar limites de threads e horários de execução.

Não é necessário instalar ferramentas das etapas posteriores agora.

### Aceite

Ambos executam as ferramentas, conhecem os caminhos utilizados e têm seu ambiente documentado.

## 7. Atividade 3 — Obtenção e verificação dos dados

### Checklist individual

- [ ] Confirmar os identificadores antes do download.

- [ ] Testar o procedimento em um run.

- [ ] Registrar download, conversão, comandos e erros.

- [ ] Converter para FASTQ conforme o layout dos dados.

- [ ] Conferir nomes, tamanhos e arquivos esperados.

- [ ] Verificar integridade dos arquivos comprimidos.

- [ ] Conferir correspondência dos mates em dados pareados.

- [ ] Registrar checksums para identificar as entradas utilizadas.

- [ ] Garantir que as seis bibliotecas estejam disponíveis e verificadas.

- [ ] Comparar sua verificação com a do colega.

Na mesma máquina, preservar uma cópia comum dos dados brutos é a opção recomendada.

## 8. Atividade 4 — FastQC e MultiQC dos dados brutos

### Checklist individual

- [ ] Executar FastQC em todos os FASTQ das seis bibliotecas.

- [ ] Preservar relatórios HTML e ZIP.

- [ ] Gerar seu próprio MultiQC dos dados brutos.

- [ ] Conferir se todos os arquivos esperados foram incluídos.

- [ ] Avaliar qualidade por posição, comprimento, adaptadores, bases indefinidas, GC, sobre-representação e duplicação.

- [ ] Preencher diagnóstico por biblioteca/run e mate.

- [ ] Apresentar sua proposta de tratamento.

A unidade de execução do FastQC é o arquivo FASTQ.

## 9. Atividade 5 — Protocolo e piloto com fastp

Antes de processar todo o conjunto, os bolsistas discutirão os resultados iniciais e apresentarão ao orientador uma proposta comum.

### Decisões a documentar

- Estratégia de remoção de adaptadores.

- Corte por qualidade, caso necessário.

- Critérios de descarte de leituras.

- Comprimento mínimo.

- Tratamento dos pares e leituras sem par.

- Comportamentos automáticos e tratamentos adicionais.

- Número de threads, caminhos e nomes de saída.

- Versão da ferramenta e comando completo.

Não assumir que definir Q20 significa cortar automaticamente todas as bases abaixo de Q20. O protocolo deverá distinguir corte de bases e filtragem de leituras.

### Checklist individual

- [ ] Contribuir com uma proposta justificada.

- [ ] Obter aprovação dos parâmetros.

- [ ] Executar o mesmo piloto com os parâmetros aprovados.

- [ ] Investigar divergências antes de ampliar a execução.

## 10. Atividade 6 — fastp nas seis bibliotecas

### Checklist individual

- [ ] Executar fastp em todas as seis bibliotecas, incluindo os runs associados.

- [ ] Utilizar o protocolo aprovado e registrar exceções autorizadas.

- [ ] Preservar os dados brutos.

- [ ] Gravar saídas em diretório exclusivo do integrante.

- [ ] Usar nomes exclusivos por run para os relatórios HTML e JSON, evitando sobrescrita.

- [ ] Atualizar a tabela de acompanhamento.

## 11. Atividade 7 — Novo FastQC e MultiQC

### Checklist individual

- [ ] Executar FastQC em todos os FASTQ processados pelo próprio estudante.

- [ ] Preservar HTML e ZIP.

- [ ] Gerar MultiQC específico dos dados processados.

- [ ] Conferir a inclusão de todos os arquivos esperados.

- [ ] Manter relatórios de dados brutos e processados separados.

- [ ] Comparar o resultado após fastp com o diagnóstico inicial.

Evitar misturar os dois conjuntos de execução em um único MultiQC sem identificação inequívoca das amostras. Cada bolsista entregará um consolidado bruto e outro processado.

## 12. Atividade 8 — Interpretação e comparação

### Tabela individual de resultados

Para cada biblioteca/run, registrar:

- Unidade de contagem: leituras ou pares.

- Quantidade de entrada.

- Quantidade retida.

- Percentual de retenção.

- Comprimento antes e depois.

- Problemas iniciais.

- Efeito do tratamento.

- Problemas persistentes.

- Recomendação e justificativa.

Calcular retenção como 100 × quantidade retida / quantidade de entrada, mantendo a mesma unidade no numerador e denominador. Não misturar pares com leituras individuais.

### Perguntas para responder

1. O tratamento reduziu os problemas observados?

2. Quanto dado foi retido em cada biblioteca?

3. O comprimento das leituras foi alterado de forma importante?

4. R1 e R2 tiveram comportamentos diferentes?

5. Alguma perda precisa de investigação?

6. Alguma biblioteca exige reprocessamento?

7. Os dois bolsistas chegaram a resultados compatíveis?

Não exigir todos os módulos verdes, um limiar universal de qualidade em todas as posições ou ausência absoluta de adaptadores como critérios automáticos de aprovação.

## 13. Caderno de laboratório

Cada estudante manterá um lablog com data, objetivo, comando, parâmetros, resultado, problema e solução.

### Registre tudo que puder no lablog

A próxima etapa será definida somente após a avaliação do orientador.

- Decidir qual ferramenta de trimming usar: Fastp ou BBduk?

- Depois disso passamos para a proxima etapa do projeto com as bibliotecas\_teste

