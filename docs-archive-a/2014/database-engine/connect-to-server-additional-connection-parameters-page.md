---
title: Connetti al server (pagina Parametri aggiuntivi per la connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638083"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="08b36-102">Connetti al server (pagina Parametri aggiuntivi per la connessione)</span><span class="sxs-lookup"><span data-stu-id="08b36-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="08b36-103">Nella finestra di dialogo di **connessione** al server di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sono disponibili le opzioni relative ai valori della stringa di connessione più comuni.</span><span class="sxs-lookup"><span data-stu-id="08b36-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="08b36-104">Usare la pagina **Parametri aggiuntivi per la connessione** per aggiungere più parametri di connessione alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="08b36-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="08b36-105">Qualsiasi parametro di connessione ODBC può costituire un parametro aggiuntivo per la connessione.</span><span class="sxs-lookup"><span data-stu-id="08b36-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="08b36-106">I parametri aggiuntivi per la connessione devono essere aggiunti nel formato **;parametro1=valore1;parametro2=valore2**.</span><span class="sxs-lookup"><span data-stu-id="08b36-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="08b36-107">I parametri aggiunti usando la pagina **Parametri aggiuntivi per la connessione** vengono aggiunti ai parametri selezionati usando le opzioni della finestra di dialogo **Connetti al server** .</span><span class="sxs-lookup"><span data-stu-id="08b36-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="08b36-108">L'ultima istanza di ogni parametro specificato sostituisce eventuali istanze precedenti del parametro stesso.</span><span class="sxs-lookup"><span data-stu-id="08b36-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="08b36-109">I parametri aggiunti tramite la pagina **Parametri aggiuntivi per la connessione** seguono e sostituiscono i parametri specificati nelle schede **Account di accesso** o **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="08b36-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="08b36-110">Se, ad esempio, nella scheda **Account di accesso** è specificato **SERVER1** come **Nome server**e la pagina **Parametri aggiuntivi per la connessione** contiene **;SERVER=SERVER2**, verrà stabilita la connessione a **SERVER2**.</span><span class="sxs-lookup"><span data-stu-id="08b36-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="08b36-111">I parametri aggiunti usando la pagina **Parametri aggiuntivi per la connessione** vengono sempre passati come testo normale.</span><span class="sxs-lookup"><span data-stu-id="08b36-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="08b36-112">Non includere credenziali di accesso e password nella pagina **Parametri aggiuntivi per la connessione** ,</span><span class="sxs-lookup"><span data-stu-id="08b36-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="08b36-113">non verranno crittografate quando vengono passate in rete.</span><span class="sxs-lookup"><span data-stu-id="08b36-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="08b36-114">Usare invece la scheda **Account di accesso** .</span><span class="sxs-lookup"><span data-stu-id="08b36-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="08b36-115">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="08b36-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="08b36-116">Per visualizzare la pagina Parametri aggiuntivi per la connessione</span><span class="sxs-lookup"><span data-stu-id="08b36-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="08b36-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]scegliere **Connessione** dal menu **Query**, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="08b36-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="08b36-118">Nella finestra di dialogo **Connetti al server** fare clic su **Opzioni**e quindi sulla scheda **Parametri aggiuntivi per la connessione** .</span><span class="sxs-lookup"><span data-stu-id="08b36-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="08b36-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="08b36-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="08b36-120">Esempio 1: Connessione al Motore di database</span><span class="sxs-lookup"><span data-stu-id="08b36-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="08b36-121">Per connettersi al database [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] in un server denominato ACCOUNTING, immettere quanto indicato di seguito nella pagina **Parametri aggiuntivi per la connessione** :</span><span class="sxs-lookup"><span data-stu-id="08b36-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="08b36-122">Esempio B: Connessione ad Analysis Services</span><span class="sxs-lookup"><span data-stu-id="08b36-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="08b36-123">Per connettersi ad Analysis Services e fare in modo che tutte le partizioni in attesa di notifiche vengano sottoposte a query in tempo reale (ignorando la memorizzazione nella cache) e per impostare il valore di timeout del writeback su 5, immettere quanto indicato di seguito nella pagina **Parametri aggiuntivi per la connessione** :</span><span class="sxs-lookup"><span data-stu-id="08b36-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
