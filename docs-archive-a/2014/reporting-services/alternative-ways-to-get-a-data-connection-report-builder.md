---
title: Modalità alternative di acquisizione di una connessione dati (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625249"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="c766d-102">Modalità alternative di acquisizione di una connessione dati (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="c766d-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="c766d-103">Una connessione dati contiene le informazioni necessarie per connettersi a un'origine dati esterna, ad esempio un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c766d-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="c766d-104">In genere, le informazioni di connessione e il tipo di credenziali da utilizzare vengono fornite dal proprietario dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c766d-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="c766d-105">Per specificare una connessione dati, è possibile utilizzare un'origine dati condivisa dal server di report o creare un'origine dati incorporata che venga utilizzata solo in un report specifico.</span><span class="sxs-lookup"><span data-stu-id="c766d-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="c766d-106">Nella maggior parte delle esercitazioni vengono utilizzate origini dati incorporate. Se tuttavia si dispone dell'accesso a origini dati condivise, sarà invece possibile utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="c766d-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="c766d-107">Recupero di una connessione dati da un'origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="c766d-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="c766d-108">Se nel server di report è disponibile un'origine dati condivisa e si dispone delle autorizzazioni necessarie per utilizzarla, sarà possibile utilizzare tale origine dati anziché un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="c766d-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="c766d-109">Nelle procedure riportate di seguito viene illustrato come individuare le origini dati condivise e fornire tutte le credenziali necessarie per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c766d-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="c766d-110">Per utilizzare un'origine dati condivisa, è necessario selezionare un server di report e un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c766d-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="c766d-111">L'URL del server di report può essere in genere recuperato dall'amministratore del server di report.</span><span class="sxs-lookup"><span data-stu-id="c766d-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="c766d-112">Per specificare una connessione dati da un elenco di origini dati condivise</span><span class="sxs-lookup"><span data-stu-id="c766d-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="c766d-113">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c766d-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="c766d-114">Verrà visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="c766d-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="c766d-115">Nell'elenco delle origini dati selezionare un'origine dati per la quale si dispone delle autorizzazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="c766d-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="c766d-116">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="c766d-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="c766d-117">Verrà visualizzato il messaggio "Creazione connessione completata".</span><span class="sxs-lookup"><span data-stu-id="c766d-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="c766d-118">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c766d-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="c766d-119">Se necessario, immettere le credenziali.</span><span class="sxs-lookup"><span data-stu-id="c766d-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="c766d-120">Per salvare in locale le credenziali, selezionare **Salva password con la connessione**.</span><span class="sxs-lookup"><span data-stu-id="c766d-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="c766d-121">Se non si seleziona questa opzione, le credenziali verranno richieste ogni volta che si esegue il report.</span><span class="sxs-lookup"><span data-stu-id="c766d-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="c766d-122">Per specificare una connessione dati selezionando il percorso a un'origine dati condivisa nel server di report</span><span class="sxs-lookup"><span data-stu-id="c766d-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="c766d-123">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c766d-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="c766d-124">Verrà visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="c766d-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="c766d-125">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="c766d-125">Click **Browse**.</span></span> <span data-ttu-id="c766d-126">Verrà visualizzata la finestra di dialogo **Seleziona origine dati** .</span><span class="sxs-lookup"><span data-stu-id="c766d-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c766d-127">Nell'elenco a discesa **Cerca in** selezionare **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="c766d-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="c766d-128">Nel riquadro dell'origine dati fare clic sull'URL del server, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c766d-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="c766d-129">Verrà visualizzato l'elenco delle origini dati o dei modelli.</span><span class="sxs-lookup"><span data-stu-id="c766d-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="c766d-130">In alternativa, in **Nome**digitare l'URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="c766d-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="c766d-131">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c766d-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="c766d-132">Verrà stabilita la connessione al server di report e verranno caricate le origini dati disponibili in corrispondenza della cartella radice.</span><span class="sxs-lookup"><span data-stu-id="c766d-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="c766d-133">Passare a una cartella che contiene un'origine dati per la quale sono disponibili sufficienti autorizzazioni di connessione, selezionare l'origine dati, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c766d-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="c766d-134">Verrà visualizzata di nuovo la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="c766d-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="c766d-135">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="c766d-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="c766d-136">Verrà visualizzato il messaggio "Creazione connessione completata".</span><span class="sxs-lookup"><span data-stu-id="c766d-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="c766d-137">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c766d-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="c766d-138">Se viene richiesto un nome utente e una password, immettere le credenziali.</span><span class="sxs-lookup"><span data-stu-id="c766d-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="c766d-139">Per salvare in locale le credenziali, selezionare **Salva password con la connessione**.</span><span class="sxs-lookup"><span data-stu-id="c766d-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c766d-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c766d-140">See Also</span></span>  
 <span data-ttu-id="c766d-141">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c766d-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="c766d-142">Esercitazioni &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="c766d-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
