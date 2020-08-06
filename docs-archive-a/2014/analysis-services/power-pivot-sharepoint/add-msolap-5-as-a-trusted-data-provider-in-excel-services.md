---
title: Aggiungere MSOLAP. 5 come provider di dati attendibile in Excel Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636427"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="ecabd-102">Aggiungere MSOLAP.5 come provider di dati attendibile in Excel Services</span><span class="sxs-lookup"><span data-stu-id="ecabd-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="ecabd-103">MSOLAP.5 si riferisce al provider OLE DB di Analysis Services per SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="ecabd-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="ecabd-104">In Excel Services questo provider deve essere considerato attendibile prima di effettuare la richiesta di connessione che comporta la disponibilità di dati PowerPivot in un server.</span><span class="sxs-lookup"><span data-stu-id="ecabd-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="ecabd-105">Se è stato configurato PowerPivot per SharePoint utilizzando lo strumento di configurazione PowerPivot, MSOLAP.5 potrebbe già essere un provider attendibile perché lo strumento include un'azione che soddisfa questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ecabd-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="ecabd-106">Se tuttavia si utilizza PowerShell o Amministrazione centrale oppure se l'azione del provider attendibile è stata esclusa nello strumento di configurazione, è possibile che il provider risulti mancante ed è quindi necessario aggiungerlo durante la configurazione della farm per l'accesso ai dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ecabd-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="ecabd-107">È sufficiente eseguire questo passaggio una volta per ogni applicazione di servizio Excel Services.</span><span class="sxs-lookup"><span data-stu-id="ecabd-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="ecabd-108">Ogni server fisico che gestisce una richiesta di dati PowerPivot, ad esempio un server PowerPivot per SharePoint o un server Excel Services, deve disporre del provider OLE DB installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="ecabd-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="ecabd-109">Un'installazione di PowerPivot per SharePoint include sempre il provider OLE DB, ma se Excel Services è in esecuzione in un computer che non dispone di PowerPivot per SharePoint, è necessario installare manualmente il provider.</span><span class="sxs-lookup"><span data-stu-id="ecabd-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="ecabd-110">Per altre informazioni, vedere [Installazione del provider OLE DB di Analysis Services nei server di SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="ecabd-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="ecabd-111">Aggiungere un provider attendibile a Excel Services</span><span class="sxs-lookup"><span data-stu-id="ecabd-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="ecabd-112">In Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**, quindi fare clic sull'applicazione di servizio Excel Services.</span><span class="sxs-lookup"><span data-stu-id="ecabd-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="ecabd-113">Fare clic su **Provider di dati attendibili**.</span><span class="sxs-lookup"><span data-stu-id="ecabd-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="ecabd-114">Verificare che MSOLAP.5 sia visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ecabd-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="ecabd-115">A seconda di come è stato configurato PowerPivot per SharePoint, MSOLAP.5 potrebbe già essere considerato attendibile.</span><span class="sxs-lookup"><span data-stu-id="ecabd-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="ecabd-116">Se non è elencato, fare clic su **Aggiungi provider di dati attendibile**.</span><span class="sxs-lookup"><span data-stu-id="ecabd-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="ecabd-117">In ID provider, digitare `MSOLAP.5`.</span><span class="sxs-lookup"><span data-stu-id="ecabd-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="ecabd-118">Per Tipo di provider, assicurarsi che sia selezionato OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ecabd-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="ecabd-119">In Descrizione provider digitare **Provider Microsoft OLE DB per OLAP Services 11.0**.</span><span class="sxs-lookup"><span data-stu-id="ecabd-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
