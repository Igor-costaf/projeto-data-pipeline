# projeto-data-pipeline
Projeto de Pipeline de Dados com Azure Blob Storage e Azure Data Factory (INGESTÃO)
1. Criar um Container no Azure Blob Storage
1.	Acessar o Portal Azure
o	Acesse portal.azure.com e faça login.
2.	Localizar ou Criar uma Conta de Armazenamento
o	No menu de pesquisa, digite Storage accounts e selecione a opção.
o	Clique em + Create para criar uma nova conta de armazenamento (se necessário).
o	Preencha os detalhes como Subscription, Resource Group, Region, Performance e Redundancy.
o	Clique em Review + Create e depois em Create.
3.	Criar um Container
o	Dentro da conta de armazenamento, vá para Containers no menu lateral.
o	Clique em + Container.
o	Nomeie o container como projeto-dados-brutos.
o	Defina o nível de acesso como Private.
o	Clique em Criar.
4.	Fazer Upload do Arquivo JSON
o	Dentro do container projeto-dados-brutos, clique em Upload.
o	Selecione o arquivo JSON (exemplo: projeto-dados.json) e clique em Upload.
________________________________________
2. Criar um Azure Data Factory (ADF)
1.	Acessar o Portal Azure
o	Acesse portal.azure.com e faça login.
2.	Criar um Data Factory
o	No menu de pesquisa, digite Data Factory e selecione a opção.
o	Clique em + Create.
o	Preencha os detalhes:
	Subscription: Escolha a assinatura.
	Resource Group: Selecione ou crie um grupo de recursos.
	Nome do Data Factory: Escolha um nome único (exemplo: meu-datafactory-projetos).
	Region: Escolha a mesma região do Blob Storage.
o	Clique em Review + Create e depois em Create.
3.	Acessar o Data Factory
o	Após a criação, clique em Go to resource.
o	No Data Factory, clique em Open Azure Data Factory Studio.
________________________________________
3. Criar um Pipeline no Data Factory
1.	Acessar o ADF Studio
o	No ADF Studio, vá para a aba Author (ícone de lápis).
2.	Criar um Novo Pipeline
o	Clique em + e selecione Pipeline → New pipeline.
o	Renomeie o pipeline para algo descritivo, como Pipeline_Ingestao_Projeto.
3.	Adicionar Atividade "Copy Data"
o	No painel de atividades, procure por Copy Data e arraste-a para o canvas.
o	Clique na atividade para configurá-la.
________________________________________
4. Configurar a Origem dos Dados (Source)
1.	Adicionar Linked Service para o Blob Storage
o	Na aba Source, clique em + New para criar um dataset.
o	Selecione Azure Blob Storage e JSON como formato.
o	Crie um Linked Service para conectar ao Blob Storage (use chave de conta ou SAS token).
2.	Configurar o Dataset
o	Navegue até o arquivo JSON no container projeto-dados-brutos.
o	Confirme as configurações e clique em OK.
________________________________________
5. Configurar o Destino dos Dados (Sink)
1.	Adicionar Linked Service para o Data Lake
o	Na aba Sink, clique em + New para criar um dataset.
o	Selecione Azure Data Lake Storage Gen2 e JSON como formato.
o	Crie um Linked Service para conectar ao Data Lake (use chave de conta ou AAD).
2.	Configurar o Dataset para o Destino
o	Defina o caminho no Data Lake (exemplo: /projeto-dados-processados/).
o	Nomeie o arquivo de destino (exemplo: dados_imoveis.json).
o	Confirme as configurações e clique em OK.
