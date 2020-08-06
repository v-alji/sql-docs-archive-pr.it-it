---
title: Visualizzazione di un log di controllo di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625279"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="e7ffa-102">Visualizzazione di un log di controllo di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7ffa-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="e7ffa-103">Questo argomento descrive come visualizzare un log di controllo di SQL Server in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7ffa-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e7ffa-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e7ffa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7ffa-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e7ffa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7ffa-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7ffa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7ffa-107">**Per visualizzare un log di controllo di SQL Server mediante:**</span><span class="sxs-lookup"><span data-stu-id="e7ffa-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="e7ffa-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7ffa-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7ffa-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e7ffa-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7ffa-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7ffa-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7ffa-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e7ffa-111">Permissions</span></span>  
 <span data-ttu-id="e7ffa-112">È necessaria l'autorizzazione `CONTROL SERVER`.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7ffa-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7ffa-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="e7ffa-114">Per visualizzare un log di controllo di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7ffa-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="e7ffa-115">In Esplora oggetti espandere la cartella **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="e7ffa-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="e7ffa-116">Espandere la cartella **Controlli** .</span><span class="sxs-lookup"><span data-stu-id="e7ffa-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="e7ffa-117">Fare clic con il pulsante destro del mouse sul log di controllo da visualizzare e selezionare **Visualizza log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="e7ffa-118">Verrà visualizzata la finestra **di dialogo Visualizzatore file di log-**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="e7ffa-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="e7ffa-119">Per altre informazioni, vedere [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="e7ffa-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="e7ffa-120">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="e7ffa-121">consiglia di visualizzare il log di controllo usando il Visualizzatore file di log.</span><span class="sxs-lookup"><span data-stu-id="e7ffa-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="e7ffa-122">Tuttavia, se si sta creando un sistema di monitoraggio automatizzato, è possibile leggere direttamente le informazioni nel file di controllo usando la funzione [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7ffa-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="e7ffa-123">La lettura diretta del file restituisce i dati in un formato leggermente diverso (non elaborato).</span><span class="sxs-lookup"><span data-stu-id="e7ffa-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="e7ffa-124">Per ulteriori informazioni **, vedere sys. fn_get_audit_file**</span><span class="sxs-lookup"><span data-stu-id="e7ffa-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ffa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7ffa-125">See Also</span></span>  
 <span data-ttu-id="e7ffa-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e7ffa-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="e7ffa-127">Scrittura di eventi di controllo di SQL Server nel registro di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7ffa-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
