---
title: Accedere al provider WMI per la gestione della configurazione tramite WQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623071"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="4ef48-102">Accedere al provider WMI per la gestione della configurazione tramite WQL</span><span class="sxs-lookup"><span data-stu-id="4ef48-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="4ef48-103">In questa sezione viene illustrato come eseguire le istruzioni WQL ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language) sul provider WMI per Gestione computer.</span><span class="sxs-lookup"><span data-stu-id="4ef48-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="4ef48-104">Nell'esempio viene utilizzato un editor WQL, WBEMtest.exe, per eseguire query WQL sul provider WMI per enumerare i servizi, i protocolli di rete e gli alias di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef48-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="4ef48-105">Esecuzione di query sui servizi mediante WBEMtest</span><span class="sxs-lookup"><span data-stu-id="4ef48-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="4ef48-106">Dal menu **Start** fare clic su **Esegui**, quindi immettere `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="4ef48-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="4ef48-107">Viene visualizzata la finestra di dialogo WBEMtest.exe.</span><span class="sxs-lookup"><span data-stu-id="4ef48-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="4ef48-108">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="4ef48-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="4ef48-109">Nel primo campo di testo digitare lo spazio dei nomi del provider WMI per Gestione computer: root\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="4ef48-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="4ef48-110">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="4ef48-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="4ef48-111">Fare clic su **Query**.</span><span class="sxs-lookup"><span data-stu-id="4ef48-111">Click **Query**.</span></span> <span data-ttu-id="4ef48-112">Digitare una query che restituisca i servizi correnti in esecuzione nel computer locale: **Select \* from SqlService.**</span><span class="sxs-lookup"><span data-stu-id="4ef48-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="4ef48-113">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="4ef48-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="4ef48-114">Ridefinire ulteriormente la query aggiungendo `WHERE ServiceName = "MSSQLSERVER"`.</span><span class="sxs-lookup"><span data-stu-id="4ef48-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
