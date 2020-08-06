---
title: Creare ed eseguire il mapping di un ambiente server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627317"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="8ecf3-102">Creare ed eseguire il mapping di un ambiente server</span><span class="sxs-lookup"><span data-stu-id="8ecf3-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="8ecf3-103">Creare un ambiente server per specificare i valori di runtime per i pacchetti contenuti in un progetto distribuito nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ecf3-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="8ecf3-104">È quindi possibile eseguire il mapping delle variabili di ambiente ai parametri, per un pacchetto specifico, per i pacchetti del punto di ingresso o per tutti i pacchetti di un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="8ecf3-105">Un pacchetto del punto di ingresso è in genere un pacchetto padre che esegue un pacchetto figlio.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8ecf3-106">Per un'esecuzione specifica, un pacchetto può essere eseguito solo con i valori contenuti in un ambiente server singolo.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="8ecf3-107">È possibile eseguire query sulle viste per un elenco di ambienti server, riferimenti all'ambiente e variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="8ecf3-108">È inoltre possibile chiamare stored procedure per aggiungere, eliminare e modificare gli ambienti, i riferimenti all'ambiente e le variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="8ecf3-109">Per ulteriori informazioni, vedere la sezione **Ambienti server, variabili del server e riferimenti all'ambiente del server** in [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8ecf3-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="8ecf3-110">Per creare e utilizzare un ambiente server</span><span class="sxs-lookup"><span data-stu-id="8ecf3-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="8ecf3-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] espandere i [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] cataloghi> nodo **SSISDB** in Esplora oggetti e individuare la cartella **ambienti** del progetto per il quale si desidera creare un ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="8ecf3-112">Fare clic con il pulsante destro del mouse sulla cartella **Ambienti** e quindi scegliere **Creazione ambiente**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="8ecf3-113">Digitare un nome e una descrizione per l'ambiente, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="8ecf3-114">Fare clic con il pulsante destro del mouse sul nuovo ambiente e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8ecf3-115">Nella pagina **Variabili** effettuare le operazioni seguenti per aggiungere una variabile.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="8ecf3-116">Selezionare il **Tipo** per la variabile.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="8ecf3-117">Il nome della variabile **non deve** corrispondere al nome del parametro del progetto di cui verrà eseguito il mapping alla variabile.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="8ecf3-118">Immettere una **Descrizione** facoltativa per la variabile.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="8ecf3-119">Immettere il **Valore** per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="8ecf3-120">Per informazioni sulle regole per i nomi delle variabili di ambiente, vedere la sezione **Variabile di ambiente** in [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8ecf3-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="8ecf3-121">Indicare se nella variabile è contenuto il valore sensibile, selezionando o deselezionando la casella di controllo **Sensibile** .</span><span class="sxs-lookup"><span data-stu-id="8ecf3-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="8ecf3-122">Se si seleziona **Sensibile**, il valore della variabile non viene visualizzato nel campo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8ecf3-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="8ecf3-123">I valori sensibili vengono crittografati nel catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="8ecf3-124">Per ulteriori informazioni sulla crittografia, vedere [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8ecf3-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="8ecf3-125">Nella pagina **Autorizzazioni** concedere o negare le autorizzazioni per gli utenti e i ruoli selezionati effettuando le operazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="8ecf3-126">Fare clic su **Sfoglia**, quindi selezionare uno o più utenti e ruoli nella finestra di dialogo **Sfoglia tutte le entità** .</span><span class="sxs-lookup"><span data-stu-id="8ecf3-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="8ecf3-127">Nell'area **Account di accesso o ruoli** selezionare l'utente o il ruolo per cui si desidera concedere o negare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="8ecf3-128">Nell'area **Esplicita** fare clic su **Concedi** o **Nega** accanto a ogni autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="8ecf3-129">Per creare lo script dell'ambiente, fare clic su **Script**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="8ecf3-130">Per impostazione predefinita, lo script viene visualizzato in una nuova finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8ecf3-131">È necessario fare clic su **Script** dopo aver apportato una o più modifiche alle proprietà dell'ambiente, ad esempio se si aggiunge una variabile, e prima di fare clic su **OK** nella finestra di dialogo **Proprietà ambiente**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="8ecf3-132">In caso contrario, non viene creato alcuno script.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="8ecf3-133">Fare clic su **OK** per salvare le modifiche apportate alle proprietà di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="8ecf3-134">Nel nodo **SSISDB** in Esplora oggetti espandere la cartella **Progetti** , fare clic con il pulsante destro del mouse sul progetto e quindi fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="8ecf3-135">Nella pagina **Riferimenti** fare clic su **Aggiungi** per aggiungere un ambiente, quindi scegliere **OK** per salvare il riferimento all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="8ecf3-136">Fare nuovamente clic con il pulsante destro del mouse sul progetto e quindi scegliere **Configura**.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="8ecf3-137">Per eseguire il mapping della variabile di ambiente a un parametro aggiunto al pacchetto in fase di progettazione o a un parametro che è stato generato durante la conversione del progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al modello di distribuzione del progetto, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="8ecf3-138">Nella scheda **Parametri** della pagina **Parametri** fare clic sul pulsante Sfoglia accanto al campo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8ecf3-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="8ecf3-139">Fare clic su **Usa variabile di ambiente**, quindi selezionare la variabile di ambiente creata.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="8ecf3-140">Per eseguire il mapping della variabile di ambiente a una proprietà di gestione connessione, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="8ecf3-141">I parametri vengono automaticamente generati nel server SSIS per le proprietà di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="8ecf3-142">Nella scheda **Gestioni connessioni** della pagina **Parametri** fare clic sul pulsante Sfoglia accanto al campo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="8ecf3-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="8ecf3-143">Fare clic su **Usa variabile di ambiente**, quindi selezionare la variabile di ambiente creata.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="8ecf3-144">Fare due volte clic su **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ecf3-144">Click **OK** twice to save your changes.</span></span>  
  
  
