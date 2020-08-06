---
title: File di query collegamento (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714468"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="92d24-102">File di query collegamento (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="92d24-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="92d24-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]usare i file di query collegamento per connettersi rapidamente e caricare i dati usati di frequente.</span><span class="sxs-lookup"><span data-stu-id="92d24-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="92d24-104">È possibile utilizzarli anche quando si desidera condividere dati MDS con gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="92d24-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="92d24-105">Anziché salvare il foglio di lavoro e inviarlo tramite posta elettronica, è necessario salvare un file di query collegamento e inviarlo tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="92d24-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="92d24-106">In tal modo si assicura la connessione al repository MDS per il mittente e il destinatario in modo da ottenere gli ultimi dati.</span><span class="sxs-lookup"><span data-stu-id="92d24-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="92d24-107">I file di query collegamento sono file XML che contengono informazioni su:</span><span class="sxs-lookup"><span data-stu-id="92d24-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="92d24-108">La connessione al repository MDS.</span><span class="sxs-lookup"><span data-stu-id="92d24-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="92d24-109">Il modello, la versione e l'entità.</span><span class="sxs-lookup"><span data-stu-id="92d24-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="92d24-110">Qualsiasi filtro applicato quando è stato creato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="92d24-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="92d24-111">L'ordine da sinistra a destra delle colonne quando è stato creato il collegamento.</span><span class="sxs-lookup"><span data-stu-id="92d24-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="92d24-112">È possibile salvare questi file in un elenco e scegliere quello desiderato quando si apre il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="92d24-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="92d24-113">È possibile esportarli nel proprio computer o in un percorso condiviso o è possibile inviarli ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="92d24-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="92d24-114">Applicazione QueryOpener</span><span class="sxs-lookup"><span data-stu-id="92d24-114">QueryOpener Application</span></span>  
 <span data-ttu-id="92d24-115">Tutti gli utenti che installano [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] dispongono di un'applicazione, chiamata QueryOpener, installata.</span><span class="sxs-lookup"><span data-stu-id="92d24-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="92d24-116">Questa applicazione è utilizzata per aprire i file di query collegamento in [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92d24-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="92d24-117">Se si fa doppio clic su un file di query collegamento, questa applicazione viene utilizzata automaticamente per aprire il file nel componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="92d24-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="92d24-118">Quando si apre un file di query collegamento con questa applicazione, viene richiesto di rendere la connessione "sicura", cioè si è sicuri del contenuto di questo percorso.</span><span class="sxs-lookup"><span data-stu-id="92d24-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="92d24-119">Ogni volta che si contrassegna una connessione come sicura, viene aggiunta a un elenco.</span><span class="sxs-lookup"><span data-stu-id="92d24-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="92d24-120">Se si desidera deselezionare questo elenco, aprire la finestra di dialogo **Impostazioni** e nella sezione **Server aggiunti a elenco attendibili** , fare clic su **Deseleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="92d24-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="92d24-121">Il percorso predefinito per l'applicazione è *unità*: \Programmi\microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="92d24-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="92d24-122">Sono disponibili due modalità per aprire i file di query collegamento: è possibile importarli o fare doppio clic per aprirli automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92d24-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="92d24-123">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="92d24-123">Related Tasks</span></span>  
  
|<span data-ttu-id="92d24-124">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="92d24-124">Task Description</span></span>|<span data-ttu-id="92d24-125">Argomento</span><span class="sxs-lookup"><span data-stu-id="92d24-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="92d24-126">Salvare il contenuto del foglio di lavoro attivo come file di query collegamento.</span><span class="sxs-lookup"><span data-stu-id="92d24-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="92d24-127">Salvare un file di query collegamento &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="92d24-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="92d24-128">Inviare tramite posta elettronica un file di query collegamento che rappresenta il contenuto del foglio di lavoro attivo.</span><span class="sxs-lookup"><span data-stu-id="92d24-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="92d24-129">Inviare tramite posta elettronica un file di query collegamento &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="92d24-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="92d24-130">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="92d24-130">Related Content</span></span>  
  
-   [<span data-ttu-id="92d24-131">Connessioni &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="92d24-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="92d24-132">Componente aggiuntivo Master Data Services per Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="92d24-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="92d24-133">Sicurezza &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="92d24-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
