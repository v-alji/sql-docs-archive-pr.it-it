---
title: Connettersi in modalità online a un database di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 363beb7132eae92907198979fe2d9892c5d07b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721964"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a><span data-ttu-id="b6a53-102">Connettersi in modalità online a un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6a53-102">Connect in Online Mode to an Analysis Services Database</span></span>
  <span data-ttu-id="b6a53-103">È possibile connettersi direttamente a un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database esistente e modificare direttamente gli oggetti all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="b6a53-103">You can connect directly to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and directly modify objects within that database.</span></span> <span data-ttu-id="b6a53-104">In caso di connessione diretta a un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , le modifiche agli oggetti vengono implementate in modo immediato e non viene creato alcun progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a53-104">When you connect directly to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, changes to objects occur immediately and no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is created within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a><span data-ttu-id="b6a53-105">Per connettersi direttamente a un database di Analysis Services mediante gli strumenti dati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6a53-105">To Connect Directly to an Analysis Services Database by using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="b6a53-106">Aprire [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a53-106">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6a53-107">Scegliere **Apri** dal menu **File** e quindi fare clic su **Database di Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="b6a53-107">On the **File** menu, point to **Open** and then click **Analysis Services Database**.</span></span>  
  
3.  <span data-ttu-id="b6a53-108">Selezionare **Connetti a database esistente**.</span><span class="sxs-lookup"><span data-stu-id="b6a53-108">Select **Connect to existing database**.</span></span>  
  
4.  <span data-ttu-id="b6a53-109">Specificare il nome del server e il nome del database.</span><span class="sxs-lookup"><span data-stu-id="b6a53-109">Specify the server name and the database name.</span></span>  
  
     <span data-ttu-id="b6a53-110">È possibile digitare il nome del database oppure eseguire una query sul server per visualizzare i database esistenti in tale server.</span><span class="sxs-lookup"><span data-stu-id="b6a53-110">You can either type the database name or query the server to view the existing databases on the server.</span></span>  
  
5.  <span data-ttu-id="b6a53-111">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6a53-111">Click **OK**.</span></span>  
  
     <span data-ttu-id="b6a53-112">È ora possibile modificare direttamente qualsiasi oggetto all'interno del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6a53-112">You can now directly edit any objects within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a53-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a53-113">See Also</span></span>  
 <span data-ttu-id="b6a53-114">[Utilizzo di progetti e database di Analysis Services durante la fase di sviluppo](work-with-analysis-services-projects-and-databases-in-development.md) </span><span class="sxs-lookup"><span data-stu-id="b6a53-114">[Working with Analysis Services Projects and Databases During the Development Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span></span>  
 [<span data-ttu-id="b6a53-115">Creazione di modelli multidimensionali tramite SQL Server Data Tools &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="b6a53-115">Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;</span></span>](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  
