# aws-certified-ai-practitioner

Guia de Estudo AWS AI Practitioner


1. Fundamentos de IA e ML


IA, ML, Deep Learning e Data Science – As Diferenças:

- Inteligência Artificial (IA): O conceito mais amplo. O objetivo é fazer máquinas simularem a inteligência humana.
- Machine Learning (ML): Uma subárea da IA. As máquinas aprendem com dados sem serem explicitamente programadas para cada tarefa.
- Deep Learning (DL): Uma subárea do ML que utiliza redes neurais "profundas" (com muitas camadas). Todo DL é ML, mas nem todo ML é DL. É especialmente poderoso para analisar imagens e texto.
- Data Science: O processo completo de extrair insights e resolver problemas usando dados. O ML é uma das ferramentas mais importantes no arsenal de um cientista de dados.
- IA Generativa: O foco do momento! É a capacidade de criar conteúdo novo e original (texto, imagem, som, código). É uma parte da IA/ML, impulsionada por tecnologias como LLMs e GANs.

Tipos de Aprendizado de Máquina:

- Supervisionado: Você fornece os dados de treino com as "respostas certas" (rótulos). Ideal para:
	- Classificação: (Ex: spam ou não spam?)
	- Regressão: (Ex: prever o preço de uma casa)
- Não Supervisionado: Os dados não têm rótulos. O algoritmo encontra padrões e estruturas por conta própria. Ideal para:
	- Agrupamento (Clustering): (Ex: segmentar clientes com perfis semelhantes)
	- Detecção de Anomalias: (Ex: identificar fraudes bancárias)
- Por Reforço (Reinforcement Learning): Um "agente" aprende por tentativa e erro, recebendo "recompensas" ou "punições" por suas ações em um ambiente.
	- Exemplo: Um robô aprendendo a andar ou um carro autônomo na AWS DeepRacer.

Ciclo de Vida de um Projeto de ML

1. Entendimento e Coleta de Dados: Definir o problema de negócio e coletar os dados necessários (Amazon S3, AWS Data Exchange).
2. Exploração e Análise (EDA): Entender os padrões, anomalias e características dos dados (SageMaker Studio, Notebooks Jupyter).
3. Limpeza e Pré-processamento: Formatar, limpar erros, tratar valores ausentes e criar novas features (SageMaker Data Wrangler, AWS Glue DataBrew).
4. Divisão de Dados (Treino/Validação/Teste): Separar os dados para garantir que o modelo seja avaliado em dados que ele nunca viu, evitando que ele "decore" as respostas.
5. Seleção e Treinamento do Algoritmo: Escolher o modelo adequado e treiná-lo com os dados (SageMaker Training, algoritmos built-in, TensorFlow, PyTorch).
6. Avaliação do Modelo: Medir a performance do modelo com métricas de negócio e estatísticas (SageMaker Clarify).
7. Implementação/Implantação (Deploy): Colocar o modelo em produção para fazer previsões (SageMaker Endpoints em tempo real, SageMaker Batch Transform para lotes).
8. Monitoramento e Manutenção: Observar o desempenho do modelo ao longo do tempo para detectar "envelhecimento" ou perda de performance (SageMaker Model Monitor, Amazon CloudWatch).
9. Documentação e Governança: Registrar todas as etapas, decisões e resultados do projeto (SageMaker Model Registry, Model Cards).

Lembre-se: É um ciclo! Frequentemente, é necessário voltar a etapas anteriores para refinar o processo.

---

2. Serviços de IA da AWS


IA Pré-treinada (Serviços de IA)

- O que são? Serviços prontos para usar, com modelos que a AWS já treinou. Você só precisa enviar seus dados via API e recebe o resultado. É a maneira mais fácil de adicionar inteligência a uma aplicação.
- Pra que serve? Para tarefas como reconhecimento de imagens e vídeos (Rekognition), converter fala em texto e vice-versa (Transcribe, Polly), traduzir (Translate), analisar textos (Comprehend), criar chatbots (Lex), prever séries temporais (Forecast), extrair texto de documentos (Textract), buscar informações (Kendra) e personalizar recomendações (Personalize).
- Vantagem: Rápido, fácil de integrar, paga por uso, e a AWS cuida de toda a infraestrutura e manutenção dos modelos.

Plataforma de ML (Amazon SageMaker)

- O que é? A plataforma central para quem quer construir, treinar e implantar seus próprios modelos de ML. É um ambiente completo que cobre todo o ciclo de vida.
- Pra que serve? Preparar dados, desenvolver em notebooks, treinar em larga escala, ajustar hiperparâmetros, implementar e gerenciar modelos.
- Vantagem: Infraestrutura sob demanda (GPU/CPU), ferramentas integradas, cobre o ciclo completo do ML sem gerenciar servidores.
---

3. Amazon SageMaker


Componentes Chave:

- SageMaker Studio: IDE (ambiente de desenvolvimento integrado) para todo o ciclo de ML.
- SageMaker Notebooks: Instâncias Jupyter pré-configuradas para experimentação.
- SageMaker Data Labeling (Ground Truth): Ajuda humana para rotular dados para ML supervisionado.
- SageMaker Data Wrangler: Ferramenta visual para preparar e agregar dados.
- SageMaker Training: Para treinamento de modelos em larga escala.
- SageMaker Algorithms: Algoritmos built-in otimizados pela AWS.
- SageMaker Hyperparameter Tuning: Encontra automaticamente os melhores hiperparâmetros para o seu modelo.
- SageMaker Hosting (Endpoints): Implantação de modelos para inferência em tempo real.
- SageMaker Batch Transform: Implantação de modelos para inferência em lote (offline).
- SageMaker Model Monitor: Monitora modelos em produção para detectar desvios de performance.
- SageMaker Clarify: Ajuda a detectar viés no modelo e a entender suas decisões (explicabilidade).
- SageMaker Model Registry: Catálogo centralizado para gerenciar e versionar modelos.
- SageMaker Pipelines: Automação (CI/CD) de todo o ciclo de vida do ML.

Fluxo de Trabalho Típico no SageMaker:

1. Começa no Studio ou Notebooks para experimentar.
2. Usa Data Wrangler ou Ground Truth para preparar os dados.
3. Treina o modelo usando Training com algoritmos built-in ou frameworks.
4. Ajusta o modelo com Hyperparameter Tuning.
5. Avalia o viés e a explicabilidade com Clarify.
6. Implanta com Hosting ou Batch Transform.
7. Gerencia e automatiza com Model Registry e Pipelines.
---

4. Fundamentos de IA Generativa (A Revolução!)

- O que é? Uma área da IA focada em criar conteúdo novo e original, como texto, imagem, áudio e código.
- Como funciona? Usa Modelos Fundacionais (FMs), que são modelos de ML gigantes treinados com uma quantidade massiva de dados.

Modelos Fundacionais (FMs)

- O que são? Modelos pré-treinados em larga escala, que servem como base para a IA Generativa.
- Tipos: LLMs (Large Language Models) para texto, modelos de difusão para imagens, etc.
- Características: São "generalistas" (podem realizar várias tarefas), mas podem ser adaptados para tarefas específicas através de fine-tuning ou RAG.

Large Language Models (LLMs)

- O que são? FMs focados em entender e gerar linguagem humana.
- Como usar?
	- Engenharia de Prompt: A arte de escrever as "perguntas" (prompts) certas para obter as melhores respostas do LLM.
	- Fine-tuning (Ajuste Fino): Re-treinar um FM pré-treinado com seus próprios dados para especializá-lo em uma tarefa.
	- RAG (Retrieval Augmented Generation): Combinar um LLM com uma busca de informações em sua base de dados privada. Isso permite que o LLM gere respostas mais precisas e contextualizadas, reduzindo "alucinações".

Serviços AWS para IA Generativa:

- Amazon Bedrock: Serviço gerenciado que oferece acesso fácil a FMs de ponta (Anthropic, Stability AI, Cohere, Amazon, etc.) via API.
- Amazon Titan: A família de FMs desenvolvidos pela própria AWS, disponível no Bedrock.
- SageMaker JumpStart: Um hub com soluções prontas e FMs para implantar rapidamente no SageMaker.
- Bancos de Dados Vetoriais: Essenciais para RAG. Armazenam representações numéricas (vetores) do seu texto para busca de similaridade. Exemplos na AWS: Kendra, OpenSearch.
---

5. Aplicações de Modelos Fundacionais


Usando FMs Pré-treinados:

- No Amazon Bedrock: Acesso mais fácil, via API, sem gerenciar infraestrutura.
- No SageMaker JumpStart: Maior controle, implantando o modelo na sua própria infraestrutura SageMaker.

Fine-tuning de FMs:

- Pra que? Para especializar um modelo em uma tarefa, jargão ou domínio específico.
- Onde? Principalmente no Amazon SageMaker.

Retrieval Augmented Generation (RAG):

- O que é? Combinar a capacidade de um LLM com a busca em seus dados privados para obter respostas precisas e confiáveis.
- Fluxo Típico:
	1. Seus dados (documentos, PDFs) são processados e transformados em vetores (embeddings).
	2. Esses vetores são armazenados em um banco de dados vetorial.
	3. Quando um usuário faz uma pergunta, o sistema busca os trechos mais relevantes no banco de dados vetorial.
	4. A pergunta do usuário + os trechos encontrados são enviados ao LLM.
	5. O LLM usa esse contexto adicional para gerar uma resposta precisa e baseada nos seus dados.
- Vantagem: Reduz o risco do LLM "inventar" informações (alucinação) e mantém as respostas atualizadas com seus dados.
---

6. Diretrizes de IA Responsável

- Princípios: Justiça (Fairness), explicabilidade, governança, transparência, segurança e privacidade.

Viés (Bias) em ML

- O que é? Quando um modelo produz resultados sistematicamente injustos ou preconceituosos, geralmente por ter aprendido com dados enviesados.
- Como mitigar? Usar dados de treino de alta qualidade e representativos e ferramentas como o SageMaker Clarify para detectar viés.

Explicabilidade (XAI)

- O que é? A capacidade de entender e explicar por que um modelo tomou uma determinada decisão. É crucial para confiança, auditoria e depuração.
- Ferramentas: SageMaker Clarify e Model Cards (documentação do modelo).
---

7. Segurança, Conformidade e Governança

- Segurança em ML:
	- IAM: Para controlar quem pode acessar os serviços e dados de ML.
	- Criptografia: Proteger dados em repouso (no S3) e em trânsito.
	- Amazon Macie: Para descobrir e proteger dados sensíveis no S3.
	- AWS CloudTrail: Para monitorar e auditar todas as chamadas de API na sua conta.
- Governança de Dados: Organizar, catalogar e gerenciar o ciclo de vida dos dados usados em IA.
- Conformidade: Garantir que o uso de dados e modelos adere a regulações como LGPD e GDPR.
- Frameworks de Governança: Criar políticas internas para o uso ético e seguro da IA.
---

8. Outros Serviços de IA da AWS


Amazon Rekognition

- O que faz: Análise de imagens e vídeos (detecta objetos, rostos, texto, modera conteúdo).
- Casos de uso: Busca de imagens por conteúdo, segurança patrimonial, moderação de mídias sociais.

Amazon Comprehend

- O que faz: Análise de linguagem natural (identifica sentimento, entidades, informações sensíveis - PII).
- Casos de uso: Análise de feedback de clientes, moderação de comentários, conformidade.

Amazon Transcribe

- O que faz: Converte áudio em texto (transcrição de fala).
- Casos de uso: Legendas automáticas, transcrição de reuniões, análise de chamadas de call center.

Amazon Polly

- O que faz: Converte texto em áudio com vozes realistas (texto para fala).
- Casos de uso: Audiolivros, assistentes de voz, sistemas de atendimento telefônico (IVR).

Amazon Translate

- O que faz: Traduz texto entre múltiplos idiomas.
- Casos de uso: Tradução de websites, suporte ao cliente multilíngue.

Amazon Lex

- O que faz: Permite construir chatbots e assistentes virtuais conversacionais. É a tecnologia por trás da Alexa.
- Casos de uso: Chatbots de atendimento, interfaces de voz para aplicativos.

Amazon Textract

- O que faz: Extrai texto, dados de formulários e tabelas de documentos (PDFs, imagens).
- Casos de uso: Automação de processamento de faturas, digitalização de formulários.

Amazon Forecast

- O que faz: Usa ML para fazer previsões de séries temporais.
- Casos de uso: Previsão de demanda de produtos, planejamento de estoque e recursos.

Amazon Personalize

- O que faz: Cria motores de recomendação personalizados.
- Casos de uso: Recomendações de produtos em e-commerce, sugestão de conteúdo em streaming.

Amazon Kendra

- O que faz: Um motor de busca inteligente para empresas, que usa ML para entender a intenção da pergunta e encontrar respostas precisas em documentos internos.
- Casos de uso: Portais de busca internos (intranet), FAQs inteligentes para suporte.
---

9. Casos de Uso Comuns de IA/ML na AWS

- Atendimento ao Cliente:
	- Chatbots e Voicebots: Lex, Polly, Transcribe.
	- Análise de sentimento do cliente: Comprehend.
- Otimização de Operações:
	- Previsão de demanda e estoque: Forecast, SageMaker.
	- Manutenção preditiva de equipamentos: SageMaker.
- Melhora da Experiência do Cliente:
	- Recomendações e conteúdo personalizado: Personalize.
	- Marketing direcionado (segmentação, previsão de churn): SageMaker.
- Processamento de Conteúdo e Mídia:
	- Transcrição e legendagem: Transcribe.
	- Moderação de conteúdo: Rekognition, Comprehend.
	- Análise de documentos: Textract.
- Segurança e Detecção de Fraude:
	- Detecção de anomalias financeiras: SageMaker.
	- Identificação de dados sensíveis: Macie, Comprehend.
- IA Generativa:
	- Geração de texto, código e imagens: Bedrock, SageMaker.
	- Sumarização de documentos: Bedrock, Comprehend.
	- Chatbots avançados: Bedrock + Lex.
---

10. Boas Práticas e Considerações em Projetos de ML

- Custo: Lembre-se que Batch Transform é mais barato que endpoints em tempo real para inferências não instantâneas.
- Escalabilidade: Use o auto scaling dos endpoints do SageMaker para lidar com picos de demanda.
- Disponibilidade: Implante modelos em múltiplas Zonas de Disponibilidade para alta resiliência.
- Segurança: Use IAM, VPC e Criptografia como base para proteger seus ativos de ML.
- Privacidade: Anonimize dados sempre que possível e use Amazon Macie para identificar dados sensíveis.
- Viés e Justiça: Use o SageMaker Clarify em projetos cujas decisões impactam pessoas (crédito, contratação).
- Explicabilidade: Modelos complexos exigem ferramentas como o SageMaker Clarify para serem compreendidos.
- Monitoramento: É vital monitorar a performance do modelo para detectar degradação (drift) e saber quando retreinar.
- MLOps: Automatize todo o ciclo de vida do ML usando SageMaker Pipelines e Model Registry.
