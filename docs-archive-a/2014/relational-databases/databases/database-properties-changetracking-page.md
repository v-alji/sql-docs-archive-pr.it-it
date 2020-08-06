---
title: Proprietà database (pagina Rilevamento modifiche) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718240"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="5f6f2-102">Proprietà database (pagina ChangeTracking)</span><span class="sxs-lookup"><span data-stu-id="5f6f2-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="5f6f2-103">Utilizzare questa pagina per visualizzare o modificare le impostazioni di rilevamento delle modifiche per il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="5f6f2-104">Per altre informazioni sulle opzioni disponibili in questa pagina, vedere [Abilitare e disabilitare il rilevamento delle modifiche &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f6f2-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f6f2-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5f6f2-105">Options</span></span>  
 <span data-ttu-id="5f6f2-106">**Rilevamento delle modifiche**</span><span class="sxs-lookup"><span data-stu-id="5f6f2-106">**Change Tracking**</span></span>  
 <span data-ttu-id="5f6f2-107">Consente di abilitare o disabilitare il rilevamento delle modifiche per il database.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="5f6f2-108">Per abilitare il rilevamento delle modifiche, è necessario disporre dell'autorizzazione per modificare il database.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="5f6f2-109">L'impostazione del valore su **True** consente di impostare un'opzione del database che consente l'abilitazione del rilevamento delle modifiche nelle singole tabelle.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="5f6f2-110">È anche possibile configurare il rilevamento delle modifiche usando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f6f2-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="5f6f2-111">**Periodo di conservazione**</span><span class="sxs-lookup"><span data-stu-id="5f6f2-111">**Retention Period**</span></span>  
 <span data-ttu-id="5f6f2-112">Specifica il periodo minimo di conservazione delle informazioni sul rilevamento delle modifiche nel database.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="5f6f2-113">I dati vengono rimossi solo se il valore **Pulizia automatica**è impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="5f6f2-114">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="5f6f2-115">**Unità di misura del periodo di memorizzazione**</span><span class="sxs-lookup"><span data-stu-id="5f6f2-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="5f6f2-116">Specifica le unità di misura per il valore Periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="5f6f2-117">È possibile selezionare **Giorni**, **Ore**o **Minuti**.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="5f6f2-118">Il valore predefinito è **Giorni**.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="5f6f2-119">Il periodo di memorizzazione minimo è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="5f6f2-120">Non esiste un periodo di memorizzazione massimo.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="5f6f2-121">**Pulizia automatica**</span><span class="sxs-lookup"><span data-stu-id="5f6f2-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="5f6f2-122">Indica se le informazioni di rilevamento delle modifiche vengono rimosse automaticamente una volta trascorso il periodo di memorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="5f6f2-123">L'abilitazione di **Pulizia automatica** reimposta i precedenti periodi di memorizzazione personalizzati al periodo di memorizzazione predefinito di 2 giorni.</span><span class="sxs-lookup"><span data-stu-id="5f6f2-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6f2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f6f2-124">See Also</span></span>  
 <span data-ttu-id="5f6f2-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5f6f2-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="5f6f2-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f6f2-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
