---
title: Visualizzare gli avvisi relativi all'esecuzione di report personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711536"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="a99e7-102">Visualizzazione di avvisi relativi all'esecuzione di report personalizzati</span><span class="sxs-lookup"><span data-stu-id="a99e7-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="a99e7-103">Per i report personalizzati sono disponibili due finestre di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="a99e7-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="a99e7-104">In questo argomento vengono descritte le modalità per consentire la visualizzazione delle caselle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a99e7-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a99e7-105">Per impostazione predefinita, prima dell'esecuzione di un report personalizzato viene visualizzata la finestra di dialogo **Esegui report personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="a99e7-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="a99e7-106">Se si seleziona la casella di controllo **Non visualizzare più questo avviso** , la finestra di dialogo non verrà più visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a99e7-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="a99e7-107">Per impostazione predefinita, la finestra di dialogo **Esegui report personalizzato** viene visualizzata anche quando si apre un report personalizzato e quindi si fa clic su un collegamento a un altro report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a99e7-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="a99e7-108">La finestra di dialogo contiene il percorso del file di report personalizzato drill-through.</span><span class="sxs-lookup"><span data-stu-id="a99e7-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="a99e7-109">Se si seleziona la casella di controllo **Non visualizzare più questo avviso** , la finestra di dialogo non verrà più visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a99e7-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a99e7-110">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a99e7-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="a99e7-111">Per consentire la visualizzazione della finestra di dialogo di avviso relativa al report personalizzato principale</span><span class="sxs-lookup"><span data-stu-id="a99e7-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="a99e7-112">Connettersi a \<*Server*> \\ < *Condividi* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Dati Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="a99e7-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="a99e7-113">Fare clic con il pulsante destro del mouse `reports.xml` e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a99e7-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="a99e7-114">Modificare\*\* \<SuppressWarning> true \</SuppressWarning> in \<SuppressWarning> false \</SuppressWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="a99e7-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="a99e7-115">Riavviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a99e7-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="a99e7-116">Per consentire la visualizzazione della finestra di dialogo di avviso relativa al report personalizzato drill-through</span><span class="sxs-lookup"><span data-stu-id="a99e7-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="a99e7-117">Connettersi a \<*Server*> \\ < *Condividi* >| \<*Drive*> \Documents and Settings \\<UserProfile \> \Dati Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span><span class="sxs-lookup"><span data-stu-id="a99e7-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="a99e7-118">Fare clic con il pulsante destro del mouse `reports.xml` e scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a99e7-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="a99e7-119">Modificare \*\* \<SuppressDrillthroughWarning> true \</SuppressDrillthroughWarning> in \<SuppressDrillthroughWarning> false \</SuppressDrillthroughWarning> \*\*.</span><span class="sxs-lookup"><span data-stu-id="a99e7-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="a99e7-120">Riavviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a99e7-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99e7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a99e7-121">See Also</span></span>  
 <span data-ttu-id="a99e7-122">[Report personalizzati in Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a99e7-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="a99e7-123">[Aggiungere un report personalizzato a Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a99e7-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="a99e7-124">Usare report personalizzati con proprietà dei nodi di Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="a99e7-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
