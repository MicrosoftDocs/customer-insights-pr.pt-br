---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644119"
---
# <a name="manage-environments"></a><span data-ttu-id="b4c1a-103">Gerenciar ambientes</span><span class="sxs-lookup"><span data-stu-id="b4c1a-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b4c1a-104">Este artigo explica como criar uma nova organização e provisionar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="b4c1a-105">Inscrever-se e criar uma organização</span><span class="sxs-lookup"><span data-stu-id="b4c1a-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="b4c1a-106">Acesse o site do [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="b4c1a-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="b4c1a-107">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="b4c1a-108">Escolha o cenário de inscrição de sua preferência e selecione o link correspondente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="b4c1a-109">Aceite os termos e condições e selecione **Continuar** para começar a criar a organização.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="b4c1a-110">Depois que o ambiente for criado, você será redirecionado para [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="b4c1a-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="b4c1a-111">Use o ambiente de demonstração para explorar o aplicativo ou crie um novo ambiente seguindo as etapas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="b4c1a-112">Após especificar as configurações do ambiente, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="b4c1a-113">Você será conectado depois que o ambiente for criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="b4c1a-114">Criar um ambiente em uma organização existente</span><span class="sxs-lookup"><span data-stu-id="b4c1a-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="b4c1a-115">Há duas maneiras de criar um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="b4c1a-116">Você pode especificar uma configuração totalmente nova ou copiar algumas definições de configuração de um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="b4c1a-117">Para criar um ambiente:</span><span class="sxs-lookup"><span data-stu-id="b4c1a-117">To create an environment:</span></span>

1. <span data-ttu-id="b4c1a-118">Selecione o símbolo de **Configurações** no cabeçalho do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="b4c1a-119">Selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b4c1a-120">![Configurações do ambiente](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="b4c1a-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="b4c1a-121">Na caixa de diálogo **Criar novo ambiente**, selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="b4c1a-122">Se você quiser [copiar dados do ambiente atual](#additional-considerations-for-copy-configuration-preview), selecione **Copiar de um ambiente existente**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="b4c1a-123">Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="b4c1a-124">Forneça os detalhes a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4c1a-124">Provide the following details:</span></span>
   - <span data-ttu-id="b4c1a-125">**Nome**: o nome deste ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="b4c1a-126">Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="b4c1a-127">**Região**: a região na qual o serviço é implantado e hospedado.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="b4c1a-128">**Tipo**: selecione se você deseja criar um ambiente de produção ou área restrita.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="b4c1a-129">Opcionalmente, é possível selecionar **Configurações avançadas**:</span><span class="sxs-lookup"><span data-stu-id="b4c1a-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="b4c1a-130">**Salvar todos os dados no**: especifica onde você deseja armazenar os dados de saída gerados do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="b4c1a-131">Você terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerenciado pela equipe do Customer Insights) e Gen2 do **Azure Data Lake Storage** (seu próprio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="b4c1a-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="b4c1a-132">Por padrão, a opção de armazenamento do Customer Insights é selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b4c1a-133">Ao salvar dados no Azure Data Lake Storage, você concorda que os dados serão transferidos e armazenados na localização geográfica adequada para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="b4c1a-134">Saiba mais no Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="b4c1a-135">Atualmente, as entidades ingeridas são sempre armazenadas no data lake gerenciado do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="b4c1a-136">Oferecemos suporte apenas a contas de armazenamento do Azure Data Lake Gen2 da mesma região do Azure que você selecionou ao criar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="b4c1a-137">Oferecemos suporte somente a contas de armazenamento habilitadas para o Namespace Hierárquico (HNS) do Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="b4c1a-138">Para a opção Azure Data Lake Storage Gen2, você pode escolher entre uma opção baseada em recurso e uma opção baseada em assinatura para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="b4c1a-139">Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b4c1a-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="b4c1a-140">O nome do **Contêiner** não pode ser alterado e será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="b4c1a-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="b4c1a-141">Se você quiser usar [previsões](predictions.md), insira a URL da instância do Common Data Service no campo **Endereço do servidor** em **Usar previsões**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="b4c1a-142">Quando você executar processos, como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento especificada acima.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="b4c1a-143">Os arquivos de dados e arquivos model.json serão criados e adicionados às respectivas subpastas com base no processo executado.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="b4c1a-144">Se você criar vários ambientes do Customer Insights e optar por salvar as entidades de saída desses ambientes na sua conta de armazenamento, pastas separadas serão criadas para cada ambiente com ci_<environmentid> no contêiner.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="b4c1a-145">Considerações adicionais para configuração de cópia (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b4c1a-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="b4c1a-146">As seguintes configurações são copiadas:</span><span class="sxs-lookup"><span data-stu-id="b4c1a-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="b4c1a-147">Configurações do recurso</span><span class="sxs-lookup"><span data-stu-id="b4c1a-147">Feature configurations</span></span>
- <span data-ttu-id="b4c1a-148">Fontes de dados ingeridas/importadas</span><span class="sxs-lookup"><span data-stu-id="b4c1a-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="b4c1a-149">Configuração de unificação de dados (Mapear, Corresponder, Mesclar)</span><span class="sxs-lookup"><span data-stu-id="b4c1a-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="b4c1a-150">Segmentos</span><span class="sxs-lookup"><span data-stu-id="b4c1a-150">Segments</span></span>
- <span data-ttu-id="b4c1a-151">Medidas</span><span class="sxs-lookup"><span data-stu-id="b4c1a-151">Measures</span></span>
- <span data-ttu-id="b4c1a-152">Relações</span><span class="sxs-lookup"><span data-stu-id="b4c1a-152">Relationships</span></span>
- <span data-ttu-id="b4c1a-153">Atividades</span><span class="sxs-lookup"><span data-stu-id="b4c1a-153">Activities</span></span>
- <span data-ttu-id="b4c1a-154">Índice de filtro e pesquisa</span><span class="sxs-lookup"><span data-stu-id="b4c1a-154">Search & filter Index</span></span>
- <span data-ttu-id="b4c1a-155">Exportar destinos</span><span class="sxs-lookup"><span data-stu-id="b4c1a-155">Export destinations</span></span>
- <span data-ttu-id="b4c1a-156">Atualização agendada</span><span class="sxs-lookup"><span data-stu-id="b4c1a-156">Scheduled refresh</span></span>
- <span data-ttu-id="b4c1a-157">Enriquecimentos</span><span class="sxs-lookup"><span data-stu-id="b4c1a-157">Enrichments</span></span>
- <span data-ttu-id="b4c1a-158">Gerenciamento de modelos</span><span class="sxs-lookup"><span data-stu-id="b4c1a-158">Model management</span></span>
- <span data-ttu-id="b4c1a-159">Atribuições de função</span><span class="sxs-lookup"><span data-stu-id="b4c1a-159">Role assignments</span></span>

<span data-ttu-id="b4c1a-160">As seguintes configurações *não* são copiadas:</span><span class="sxs-lookup"><span data-stu-id="b4c1a-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="b4c1a-161">Perfis do cliente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-161">Customer profiles.</span></span>
- <span data-ttu-id="b4c1a-162">Credenciais da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-162">Data source credentials.</span></span> <span data-ttu-id="b4c1a-163">Você precisará fornecer as credenciais para cada fonte de dados e atualizar as fontes de dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="b4c1a-164">Fontes de dados da pasta Common Data Model e do lake gerenciado do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="b4c1a-165">Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="b4c1a-166">Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="b4c1a-167">Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="b4c1a-168">Todas as fontes de dados mostrarão um status **Credenciais Necessárias**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="b4c1a-169">Edite as fontes de dados e insira as credenciais para atualizá-las.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b4c1a-170">![Fontes de dados copiadas](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="b4c1a-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="b4c1a-171">Após atualizar as fontes de dados, vá para **Dados** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="b4c1a-172">Aqui você encontrará configurações do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="b4c1a-173">Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="b4c1a-174">Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="b4c1a-175">Editar um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="b4c1a-175">Edit an existing environment</span></span>

<span data-ttu-id="b4c1a-176">Você pode editar alguns dos detalhes dos ambientes existentes.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="b4c1a-177">Vá para **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="b4c1a-178">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-178">Select **Edit**.</span></span>

3. <span data-ttu-id="b4c1a-179">Você pode atualizar o **Nome de exibição**, do ambiente, mas não pode alterar a **Região** ou o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="b4c1a-180">Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage Gen2, você poderá atualizar a **Chave da conta**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="b4c1a-181">No entanto, você não pode alterar o **Nome da conta** e o nome do **Recipiente**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="b4c1a-182">Opcionalmente, você pode atualizar de uma conexão baseada em chave de conta para uma conexão baseada em recurso ou assinatura.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="b4c1a-183">Após a atualização, não é possível reverter para a chave de conta.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="b4c1a-184">Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b4c1a-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="b4c1a-185">Você não pode alterar informações de **Contêiner** ao atualizar a conexão.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="b4c1a-186">Redefinir um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="b4c1a-186">Reset an existing environment</span></span>

<span data-ttu-id="b4c1a-187">Você pode redefinir um ambiente para um estado vazio se quiser excluir todas as configurações e remover os dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="b4c1a-188">Vá para **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="b4c1a-189">Selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="b4c1a-190">Para confirmar a exclusão, insira o nome do ambiente e selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="b4c1a-191">Excluir um ambiente existente</span><span class="sxs-lookup"><span data-stu-id="b4c1a-191">Delete an existing environment</span></span>

1. <span data-ttu-id="b4c1a-192">Vá para **Administração** > **Sistema** > **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="b4c1a-193">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-193">Select **Delete**.</span></span>

1. <span data-ttu-id="b4c1a-194">Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b4c1a-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
