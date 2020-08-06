---
title: srv_paramsetoutput (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624720"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="3ce34-102">srv_paramsetoutput (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="3ce34-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3ce34-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="3ce34-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="3ce34-104">Imposta il valore di un parametro restituito.</span><span class="sxs-lookup"><span data-stu-id="3ce34-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="3ce34-105">Questa funzione sostituisce la funzione **srv_paramset**.</span><span class="sxs-lookup"><span data-stu-id="3ce34-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce34-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ce34-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ce34-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3ce34-107">Arguments</span></span>  
 <span data-ttu-id="3ce34-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="3ce34-108">*srvproc*</span></span>  
 <span data-ttu-id="3ce34-109">Handle per una connessione client.</span><span class="sxs-lookup"><span data-stu-id="3ce34-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="3ce34-110">*n*</span><span class="sxs-lookup"><span data-stu-id="3ce34-110">*n*</span></span>  
 <span data-ttu-id="3ce34-111">Numero ordinale del parametro da impostare.</span><span class="sxs-lookup"><span data-stu-id="3ce34-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="3ce34-112">Il primo parametro è 1.</span><span class="sxs-lookup"><span data-stu-id="3ce34-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="3ce34-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="3ce34-113">*pbData*</span></span>  
 <span data-ttu-id="3ce34-114">Puntatore al valore dei dati da inviare di nuovo al client come parametro restituito della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3ce34-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="3ce34-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="3ce34-115">*cbLen*</span></span>  
 <span data-ttu-id="3ce34-116">Lunghezza effettiva dei dati da restituire.</span><span class="sxs-lookup"><span data-stu-id="3ce34-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="3ce34-117">Se il tipo di dati del parametro specifica i valori di una lunghezza costante e non consente valori Null (ad esempio, *srvbit* or *srvint1*), *cbLen* viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="3ce34-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="3ce34-118">Il valore 0 significa dati di lunghezza zero se *fNull* è FALSE.</span><span class="sxs-lookup"><span data-stu-id="3ce34-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="3ce34-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="3ce34-119">*fNull*</span></span>  
 <span data-ttu-id="3ce34-120">Flag che indica se il valore del parametro restituito è NULL.</span><span class="sxs-lookup"><span data-stu-id="3ce34-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="3ce34-121">Impostare questo flag su TRUE se il parametro deve essere impostato su NULL.</span><span class="sxs-lookup"><span data-stu-id="3ce34-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="3ce34-122">Il valore predefinito è FALSE.</span><span class="sxs-lookup"><span data-stu-id="3ce34-122">The default value is FALSE.</span></span> <span data-ttu-id="3ce34-123">Se *fNull* è impostato su TRUE, *cbLen* deve essere impostato su 0; in caso contrario la funzione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3ce34-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3ce34-124">Restituisce</span><span class="sxs-lookup"><span data-stu-id="3ce34-124">Returns</span></span>  
 <span data-ttu-id="3ce34-125">Se le informazioni sul parametro sono state impostate correttamente, viene restituito SUCCEED; in caso contrario, FAIL.</span><span class="sxs-lookup"><span data-stu-id="3ce34-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="3ce34-126">FAIL viene restituito nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="3ce34-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="3ce34-127">Il parametro non è un parametro restituito.</span><span class="sxs-lookup"><span data-stu-id="3ce34-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="3ce34-128">L'argomento *cbLen* non è valido.</span><span class="sxs-lookup"><span data-stu-id="3ce34-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce34-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3ce34-129">Remarks</span></span>  
 <span data-ttu-id="3ce34-130">**Nota sulla sicurezza** È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="3ce34-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="3ce34-131">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="3ce34-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
