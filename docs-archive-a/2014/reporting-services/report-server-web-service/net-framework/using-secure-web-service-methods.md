---
title: Using Secure Web Service Methods (Uso di metodi del servizio Web protetti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723375"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="ee461-102">Utilizzo di metodi del servizio Web protetti</span><span class="sxs-lookup"><span data-stu-id="ee461-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="ee461-103">Alcuni metodi del servizio Web ReportServer possono richiedere una connessione protetta per essere richiamati.</span><span class="sxs-lookup"><span data-stu-id="ee461-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="ee461-104">I metodi che richiedono una connessione protetta sono determinati dall'impostazione `SecureConnectionLevel` nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="ee461-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="ee461-105">Il valore dell'impostazione è un valore intero con un intervallo valido compreso tra 0 e un numero superiore.</span><span class="sxs-lookup"><span data-stu-id="ee461-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="ee461-106">Nella tabella seguente vengono descritti questi valori.</span><span class="sxs-lookup"><span data-stu-id="ee461-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="ee461-107">Level</span><span class="sxs-lookup"><span data-stu-id="ee461-107">Level</span></span>|<span data-ttu-id="ee461-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee461-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee461-109">**0**</span><span class="sxs-lookup"><span data-stu-id="ee461-109">**0**</span></span>|<span data-ttu-id="ee461-110">Livello di sicurezza basso.</span><span class="sxs-lookup"><span data-stu-id="ee461-110">Not secure.</span></span> <span data-ttu-id="ee461-111">Le chiamate effettuate all'API SOAP di Reporting Services non richiedono una connessione protetta.</span><span class="sxs-lookup"><span data-stu-id="ee461-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="ee461-112">Maggiore di **0**</span><span class="sxs-lookup"><span data-stu-id="ee461-112">Greater than **0**</span></span>|<span data-ttu-id="ee461-113">Livello di sicurezza medio.</span><span class="sxs-lookup"><span data-stu-id="ee461-113">Secure.</span></span> <span data-ttu-id="ee461-114">Tutte le chiamate effettuate all'API SOAP di Reporting Services richiedono una connessione protetta.</span><span class="sxs-lookup"><span data-stu-id="ee461-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="ee461-115">È possibile utilizzare il metodo <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> del servizio Web per restituire un elenco di metodi del servizio Web che richiedono una connessione protetta in base alla configurazione corrente del server di report.</span><span class="sxs-lookup"><span data-stu-id="ee461-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="ee461-116">In uno scenario SSL è necessario valutare l'elenco di metodi restituiti da <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> e modificare il nome dello schema dell'URI del servizio Web in "https" o "http", a seconda del metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="ee461-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee461-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee461-117">See Also</span></span>  
 <span data-ttu-id="ee461-118">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="ee461-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="ee461-119">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="ee461-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
