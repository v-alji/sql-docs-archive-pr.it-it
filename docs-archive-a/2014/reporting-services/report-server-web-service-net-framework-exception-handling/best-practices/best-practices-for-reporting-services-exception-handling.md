---
title: Procedure consigliate per la gestione delle eccezioni in Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627641"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="bb54d-102">Procedure consigliate per la gestione delle eccezioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bb54d-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="bb54d-103">Quando si sviluppano applicazioni [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], è possibile ricorrere a diversi metodi per eliminare o ridurre le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="bb54d-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="bb54d-104">Quando si verificano le eccezioni, fornire messaggi di errore chiari e concisi all'utente e aggiungere funzionalità adeguate di gestione delle eccezioni per impedire che le applicazioni vengano chiuse in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bb54d-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="bb54d-105">Un'applicazione che invia richieste al servizio Web ReportServer deve essere in grado di effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb54d-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="bb54d-106">Evitare che vengano generate eccezioni impedendo il maggior numero possibile di richieste non valide.</span><span class="sxs-lookup"><span data-stu-id="bb54d-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="bb54d-107">Rilevare le eccezioni e fornire codice specifico di gestione degli errori quando possibile.</span><span class="sxs-lookup"><span data-stu-id="bb54d-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="bb54d-108">Gestire i casi di errore che non generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="bb54d-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb54d-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="bb54d-109">In This Section</span></span>  
  
|<span data-ttu-id="bb54d-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="bb54d-110">Topic</span></span>|<span data-ttu-id="bb54d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb54d-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bb54d-112">Metodi per evitare le richieste non valide</span><span class="sxs-lookup"><span data-stu-id="bb54d-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="bb54d-113">Vengono descritte le tecniche per impedire l'invio delle richieste non valide al server di report.</span><span class="sxs-lookup"><span data-stu-id="bb54d-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="bb54d-114">Uso di blocchi try e catch</span><span class="sxs-lookup"><span data-stu-id="bb54d-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="bb54d-115">Viene descritto come migliorare l'affidabilità dell'applicazione con i blocchi try/catch.</span><span class="sxs-lookup"><span data-stu-id="bb54d-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="bb54d-116">Gestione di avvisi e casi che non provocano eccezioni</span><span class="sxs-lookup"><span data-stu-id="bb54d-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="bb54d-117">Viene illustrato come gestire gli errori che non comportano la generazione di un'eccezione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb54d-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="bb54d-118">Utilizzo della proprietà Detail per la gestione di errori specifici</span><span class="sxs-lookup"><span data-stu-id="bb54d-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="bb54d-119">Spiega come gestire errori specifici a livello di codice tramite la proprietà **Detail** dell'oggetto **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="bb54d-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb54d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb54d-120">See Also</span></span>  
 <span data-ttu-id="bb54d-121">[Proprietà Detail](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="bb54d-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="bb54d-122">[Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="bb54d-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="bb54d-123">Classe SoapException di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bb54d-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
