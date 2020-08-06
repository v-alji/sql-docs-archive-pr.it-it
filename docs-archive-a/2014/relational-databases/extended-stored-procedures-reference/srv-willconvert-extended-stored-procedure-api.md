---
title: srv_willconvert (Api Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725792"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="4470d-102">srv_willconvert (Api Stored Procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="4470d-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4470d-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="4470d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4470d-104">Determina se una conversione di un tipo di dati specifico è disponibile all'interno della Libreria ODS.</span><span class="sxs-lookup"><span data-stu-id="4470d-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4470d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4470d-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4470d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4470d-106">Arguments</span></span>  
 <span data-ttu-id="4470d-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="4470d-107">*srctype*</span></span>  
 <span data-ttu-id="4470d-108">Indica il tipo di dati da convertire.</span><span class="sxs-lookup"><span data-stu-id="4470d-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="4470d-109">Questo parametro può appartenere a qualsiasi tipo di dati dell'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="4470d-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="4470d-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="4470d-110">*desttype*</span></span>  
 <span data-ttu-id="4470d-111">Indica il tipo di dati nel quale devono essere convertiti i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="4470d-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="4470d-112">Questo parametro può appartenere a qualsiasi tipo di dati dell'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="4470d-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4470d-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="4470d-113">Returns</span></span>  
 <span data-ttu-id="4470d-114">TRUE se la conversione del tipo di dati è supportata. In caso contrario, FALSE.</span><span class="sxs-lookup"><span data-stu-id="4470d-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4470d-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4470d-115">Remarks</span></span>  
 <span data-ttu-id="4470d-116">Per una descrizione di ogni tipo di dati, vedere [Tipi di dati &#40;API Stored procedure estesa&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="4470d-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4470d-117">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="4470d-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4470d-118">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4470d-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4470d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4470d-119">See Also</span></span>  
 [<span data-ttu-id="4470d-120">srv_convert &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="4470d-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
