---
title: Finestra di dialogo Accesso a Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721041"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="cb3fd-102">Finestra di dialogo Accesso a Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="cb3fd-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="cb3fd-103">Utilizzare la finestra di dialogo **Accesso a Reporting Services** per specificare le credenziali per la pubblicazione di report nel server di report.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="cb3fd-104">**Nota** Se è la prima volta che si pubblica un report in un server di report dopo aver impostato la proprietà di distribuzione **TargetServerURL** per un progetto, verificare che il nome del server specificato sia simile a `http://localhost/reportserver` e non `http://localhost/reports` .</span><span class="sxs-lookup"><span data-stu-id="cb3fd-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="cb3fd-105">Se si specifica la directory `reports` nel server locale anziché la directory `reportserver` , verrà visualizzata questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="cb3fd-106">Per altre informazioni sull'impostazione **TargetServerURL**, vedere [Impostare le proprietà di distribuzione &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="cb3fd-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb3fd-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cb3fd-107">Options</span></span>  
 <span data-ttu-id="cb3fd-108">**Server**</span><span class="sxs-lookup"><span data-stu-id="cb3fd-108">**Server**</span></span>  
 <span data-ttu-id="cb3fd-109">Indica il nome del server di report.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-109">Displays the name of the report server.</span></span> <span data-ttu-id="cb3fd-110">Ad esempio: `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="cb3fd-111">Per i server di report che utilizzano una porta diversa da quella predefinita, ovvero 80, includere il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="cb3fd-112">Ad esempio: `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="cb3fd-113">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="cb3fd-113">**User name**</span></span>  
 <span data-ttu-id="cb3fd-114">Consente di digitare il nome utente da utilizzare per l'accesso al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="cb3fd-115">**Password**</span><span class="sxs-lookup"><span data-stu-id="cb3fd-115">**Password**</span></span>  
 <span data-ttu-id="cb3fd-116">Consente di digitare la password da utilizzare per l'accesso al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cb3fd-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3fd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb3fd-117">See Also</span></span>  
 <span data-ttu-id="cb3fd-118">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="cb3fd-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="cb3fd-119">[Specificare le credenziali e le informazioni di connessione per le origini dati del Report](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Progettazione report Guida sensibile](report-designer-f1-help.md) al contesto</span><span class="sxs-lookup"><span data-stu-id="cb3fd-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
