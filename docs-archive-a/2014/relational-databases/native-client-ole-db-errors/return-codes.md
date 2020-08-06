---
title: Codici restituiti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636050"
---
# <a name="return-codes"></a><span data-ttu-id="261f0-102">Codici restituiti</span><span class="sxs-lookup"><span data-stu-id="261f0-102">Return Codes</span></span>
  <span data-ttu-id="261f0-103">Al livello più elementare, una funzione membro può avere esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="261f0-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="261f0-104">A un livello più approfondito, una funzione può avere esito positivo, ma tale esito potrebbe non corrispondere alle previsioni dello sviluppatore dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="261f0-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="261f0-105">Per altre informazioni sui codici restituiti OLE DB, vedere [Codici restituiti (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="261f0-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="261f0-106">Quando una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzione membro del provider OLE DB di Native Client restituisce S_OK, la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="261f0-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="261f0-107">Quando una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzione membro del provider OLE DB di Native client non restituisce S_OK, l'operazione di decompressione HRESULT OLE/com non è riuscita e IS_ERROR le macro possono determinare l'esito positivo o negativo complessivo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="261f0-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="261f0-108">Se FAILED o IS_ERROR restituisce TRUE, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native client garantisce che l'esecuzione della funzione membro non sia riuscita.</span><span class="sxs-lookup"><span data-stu-id="261f0-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="261f0-109">Se ha ESITo negativo o IS_ERROR restituisce FALSE e HRESULT non è uguale S_OK, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native client ha la certezza che la funzione abbia avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="261f0-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="261f0-110">Il consumer può recuperare informazioni dettagliate su questo ritorno "success with information" dalle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfacce di errore del provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="261f0-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="261f0-111">Inoltre, nel caso in cui una funzione abbia esito negativo (la macro non riuscita restituisce TRUE), le informazioni estese sugli errori sono disponibili nelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfacce di errore del provider OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="261f0-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="261f0-112">I consumer del provider OLE DB di Native client in genere rilevano il DB_S_ERRORSOCCURRED HRESULT restituito "success with information".</span><span class="sxs-lookup"><span data-stu-id="261f0-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="261f0-113">Le funzioni membro che restituiscono DB_S_ERRORSOCCURRED definiscono in genere uno o più parametri che forniscono al consumer i valori di stato.</span><span class="sxs-lookup"><span data-stu-id="261f0-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="261f0-114">Poiché è possibile che le uniche informazioni a disposizione del consumer siano quelle restituite nei parametri dei valori di stato, è necessario implementare la logica dell'applicazione per il recupero dei valori di stato quando essi sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="261f0-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="261f0-115">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzioni membro del provider OLE DB di Native client non restituiscono il codice di esito positivo S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="261f0-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="261f0-116">Tutte le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzioni membro del provider OLE DB Native Client restituiscono sempre S_OK per indicare l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="261f0-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261f0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="261f0-117">See Also</span></span>  
 [<span data-ttu-id="261f0-118">Errori</span><span class="sxs-lookup"><span data-stu-id="261f0-118">Errors</span></span>](errors.md)  
  
  
