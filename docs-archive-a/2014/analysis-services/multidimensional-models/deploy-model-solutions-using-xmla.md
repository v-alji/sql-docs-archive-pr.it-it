---
title: Distribuire soluzioni di modelli tramite XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML scripts [Analysis Services]
- scripts [Analysis Services], deployment
- deploying [Analysis Services], XML scripts
- Analysis Services deployments, XML scripts
ms.assetid: a8cb1837-fcac-4730-bea4-a72cf94d9f7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b78490c5ab6ad3ba5e52bb82d4be254e3f5f102b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725084"
---
# <a name="deploy-model-solutions-using-xmla"></a><span data-ttu-id="b23dd-102">Distribuire soluzioni di modelli utilizzando XMLA</span><span class="sxs-lookup"><span data-stu-id="b23dd-102">Deploy Model Solutions Using XMLA</span></span>
  <span data-ttu-id="b23dd-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]l'opzione **Genera codice per istruzione CREATE in** del comando **Crea script per database** consente di creare uno script XML per un intero database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o uno dei relativi oggetti che lo costituiscono.</span><span class="sxs-lookup"><span data-stu-id="b23dd-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an entire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or one of its constituent objects.</span></span> <span data-ttu-id="b23dd-104">Lo script risultante può quindi essere eseguito in un altro computer per ricreare lo schema (metadati) del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b23dd-104">The resulting script can then be run on another computer to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="b23dd-105">Lo script genera l'intero database e non è disponibile alcun meccanismo per eseguire l'aggiornamento incrementale di oggetti già distribuiti durante l'utilizzo dello script.</span><span class="sxs-lookup"><span data-stu-id="b23dd-105">The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script.</span></span> <span data-ttu-id="b23dd-106">In seguito all'esecuzione dello script e alla distribuzione del database, il nuovo database creato deve essere elaborato prima che gli utenti possano visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="b23dd-106">After running the script and deploying the database, the newly created database must be processed before users can browse it.</span></span>  
  
 <span data-ttu-id="b23dd-107">Per altre informazioni sul comando **Crea script per database** , vedere [Documentazione e script per un database di Analysis Services](document-and-script-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="b23dd-107">For more information about the **Script Database As** command, see [Document and Script an Analysis Services Database](document-and-script-an-analysis-services-database.md).</span></span>  
  
## <a name="modifying-object-properties-in-the-xml-script"></a><span data-ttu-id="b23dd-108">Modifica delle proprietà degli oggetti nello script XML</span><span class="sxs-lookup"><span data-stu-id="b23dd-108">Modifying Object Properties in the XML Script</span></span>  
 <span data-ttu-id="b23dd-109">Quando si usa il comando **Crea script per database** , non è possibile modificare proprietà specifiche, ad esempio il nome del database, le stringhe di connessione dell'origine dei dati e le impostazioni di sicurezza, degli oggetti del database.</span><span class="sxs-lookup"><span data-stu-id="b23dd-109">When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects.</span></span> <span data-ttu-id="b23dd-110">Tali proprietà devono essere modificate manualmente nello script in seguito alla generazione dello script oppure nel database distribuito in seguito all'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="b23dd-110">These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b23dd-111">La password eventualmente specificata nella stringa di connessione per un'origine dati o ai fini della rappresentazione non è contenuta nello script XML.</span><span class="sxs-lookup"><span data-stu-id="b23dd-111">The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes.</span></span> <span data-ttu-id="b23dd-112">Poiché in tale scenario la password è necessaria per l'elaborazione, è necessario aggiungerla manualmente allo script XML prima che questo venga eseguito oppure aggiungerla dopo l'esecuzione dello script XML.</span><span class="sxs-lookup"><span data-stu-id="b23dd-112">Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23dd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b23dd-113">See Also</span></span>  
 <span data-ttu-id="b23dd-114">[Distribuire soluzioni di modelli tramite la distribuzione guidata](deploy-model-solutions-using-the-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="b23dd-114">[Deploy Model Solutions Using the Deployment Wizard](deploy-model-solutions-using-the-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="b23dd-115">Sincronizzare database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b23dd-115">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)  
  
  
