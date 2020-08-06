---
title: rsModelGenerationError - Errore di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629163"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="6159f-102">rsModelGenerationError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6159f-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="6159f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6159f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6159f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6159f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6159f-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="6159f-105">Event ID</span></span>|<span data-ttu-id="6159f-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="6159f-106">rsRenderingError</span></span>|  
|<span data-ttu-id="6159f-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6159f-107">Event Source</span></span>|<span data-ttu-id="6159f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="6159f-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="6159f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6159f-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="6159f-110">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6159f-110">Message Text</span></span>|<span data-ttu-id="6159f-111">Errore durante la generazione del modello.</span><span class="sxs-lookup"><span data-stu-id="6159f-111">An error occurred while generating model.</span></span> <span data-ttu-id="6159f-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="6159f-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6159f-113">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6159f-113">Explanation</span></span>  
 <span data-ttu-id="6159f-114">Il modello di report non è stato generato.</span><span class="sxs-lookup"><span data-stu-id="6159f-114">The report model could not be generated.</span></span> <span data-ttu-id="6159f-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP1 e versioni precedenti questo errore viene visualizzato con maggior probabilità quando l'oggetto System.Data.DataSet non riesce a gestire una tabella o una relazione all'interno dello schema del database, ad esempio quando vengono definite due chiavi esterne nella stessa colonna di una tabella.</span><span class="sxs-lookup"><span data-stu-id="6159f-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6159f-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6159f-116">User Action</span></span>  
 <span data-ttu-id="6159f-117">Per determinare il motivo specifico che ha causato la visualizzazione del messaggio, esaminare i file di log del server di report, nel percorso \Microsoft SQL Server\\<Istanza di SQL Server\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="6159f-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="6159f-118">Solo interno</span><span class="sxs-lookup"><span data-stu-id="6159f-118">Internal-Only</span></span>  
  
