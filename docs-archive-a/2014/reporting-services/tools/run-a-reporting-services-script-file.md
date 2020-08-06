---
title: Eseguire un file script di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721000"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="cc0db-102">Eseguire un file script di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cc0db-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="cc0db-103">- I file script vengono eseguiti dal prompt dei comandi usando l'ambiente di script di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="cc0db-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="cc0db-104">RS.exe dispone di molti argomenti del prompt dei comandi disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cc0db-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="cc0db-105">Per altre informazioni sulle opzioni del prompt dei comandi, vedere [Utilità RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cc0db-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="cc0db-106">Per altri esempi di script, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="cc0db-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="cc0db-107">Esempi di righe di comando</span><span class="sxs-lookup"><span data-stu-id="cc0db-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="cc0db-108">Eseguire Script.rss nell'ambiente di script che definisce il server di report di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cc0db-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="cc0db-109">Per impostazione predefinita, viene applicata l'autenticazione di Windows:</span><span class="sxs-lookup"><span data-stu-id="cc0db-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="cc0db-110">Eseguire Script.rss nell'ambiente di script che specifica un nome utente e una password per l'autenticazione delle chiamate al servizio Web:</span><span class="sxs-lookup"><span data-stu-id="cc0db-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="cc0db-111">Eseguire Script.rss nell'ambiente di script che specifica un timeout del server di 30 secondi:</span><span class="sxs-lookup"><span data-stu-id="cc0db-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="cc0db-112">Eseguire Script.rss nell'ambiente di script che specifica una variabile globale degli script denominata *report*.</span><span class="sxs-lookup"><span data-stu-id="cc0db-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="cc0db-113">Eseguire Script.rss nell'ambiente di script che specifica che le operazioni del servizio Web nel file script vengono eseguite come batch.</span><span class="sxs-lookup"><span data-stu-id="cc0db-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cc0db-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc0db-114">See Also</span></span>  
 [<span data-ttu-id="cc0db-115">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cc0db-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
