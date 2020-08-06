---
title: Visualizzare o modificare i percorsi predefiniti per i file di dati e di log (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713468"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="3a2a0-102">Visualizzazione o modifica dei percorsi predefiniti per i file di dati e di log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3a2a0-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3a2a0-103">In questo argomento si descrive come visualizzare e modificare i percorsi predefiniti dei nuovi file di dati e di log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a2a0-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="3a2a0-104">Il percorso predefinito viene ottenuto dal Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="3a2a0-105">Dopo la modifica, il percorso viene utilizzato in tutti i nuovi database creati nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se non è specificato un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="3a2a0-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3a2a0-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a2a0-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3a2a0-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3a2a0-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="3a2a0-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="3a2a0-109">**Per visualizzare o modificare i percorsi predefiniti per i file di dati e di log utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="3a2a0-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="3a2a0-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a2a0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="3a2a0-111">**Completamento:**  [Modifica dei percorsi predefiniti](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3a2a0-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a2a0-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3a2a0-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3a2a0-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="3a2a0-113">Recommendations</span></span>  
 <span data-ttu-id="3a2a0-114">La procedura consigliata per la protezione dei file di dati e di log consiste nel verificare che siano protetti da elenchi di controllo di accesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="3a2a0-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="3a2a0-115">Gli elenchi di controllo di accesso devono essere impostati a livello della radice in cui vengono creati i file.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a2a0-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a2a0-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a2a0-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3a2a0-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a2a0-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a2a0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="3a2a0-119">Per visualizzare o modificare i percorsi predefiniti per i file di database</span><span class="sxs-lookup"><span data-stu-id="3a2a0-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="3a2a0-120">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3a2a0-121">Nel pannello sinistro fare clic sulla pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="3a2a0-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="3a2a0-122">Nel pannello **Percorsi predefiniti database**è possibile visualizzare i percorsi predefiniti correnti per i nuovi file di dati e di log.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="3a2a0-123">Per modificare un percorso predefinito, immettere un nuovo percorso predefinito nel campo **Dati** o **Log** oppure fare clic sul pulsante Sfoglia per individuare e selezionare un percorso.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="3a2a0-124">Completamento: dopo la modifica dei percorsi predefiniti</span><span class="sxs-lookup"><span data-stu-id="3a2a0-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="3a2a0-125">È necessario arrestare e avviare il servizio SQL Server per completare la modifica.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2a0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a2a0-126">See Also</span></span>  
 <span data-ttu-id="3a2a0-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a2a0-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="3a2a0-128">Creare un database</span><span class="sxs-lookup"><span data-stu-id="3a2a0-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
