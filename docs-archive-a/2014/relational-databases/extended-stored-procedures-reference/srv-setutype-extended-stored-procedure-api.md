---
title: srv_setutype (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723884"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="21d23-102">srv_setutype (API Stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="21d23-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="21d23-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="21d23-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="21d23-104">Imposta il tipo di dati definito dall'utente per una colonna di una riga.</span><span class="sxs-lookup"><span data-stu-id="21d23-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d23-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21d23-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="21d23-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="21d23-106">Arguments</span></span>  
 <span data-ttu-id="21d23-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="21d23-107">*srvproc*</span></span>  
 <span data-ttu-id="21d23-108">Puntatore alla struttura SRV_PROC che rappresenta l'handle di una determinata connessione client.</span><span class="sxs-lookup"><span data-stu-id="21d23-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="21d23-109">La struttura contiene informazioni utilizzate dalla libreria dell'API Stored procedure estesa per gestire le comunicazioni e i dati tra l'applicazione e il client.</span><span class="sxs-lookup"><span data-stu-id="21d23-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="21d23-110">*column*</span><span class="sxs-lookup"><span data-stu-id="21d23-110">*column*</span></span>  
 <span data-ttu-id="21d23-111">Indica quale colonna impostare.</span><span class="sxs-lookup"><span data-stu-id="21d23-111">Indicates which column to set.</span></span> <span data-ttu-id="21d23-112">Le colonne sono numerate a partire da 1.</span><span class="sxs-lookup"><span data-stu-id="21d23-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="21d23-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="21d23-113">*user_type*</span></span>  
 <span data-ttu-id="21d23-114">Specifica il codice del tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="21d23-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="21d23-115">Restituisce</span><span class="sxs-lookup"><span data-stu-id="21d23-115">Returns</span></span>  
 <span data-ttu-id="21d23-116">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="21d23-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="21d23-117">Restituisce FAIL se la colonna non esiste.</span><span class="sxs-lookup"><span data-stu-id="21d23-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d23-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="21d23-118">Remarks</span></span>  
 <span data-ttu-id="21d23-119">In una colonna sono presenti due tipi di dati: il tipo di dati effettivo e il tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="21d23-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="21d23-120">Il tipo di dati definito dall'utente viene utilizzato da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per archiviare il tipo di dati effettivo definito dall'utente, se presente, e le informazioni sulla descrizione della colonna, ad esempio il supporto di valori null e aggiornabilità, per la colonna.</span><span class="sxs-lookup"><span data-stu-id="21d23-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="21d23-121">La funzione **srv_setutype** può essere chiamata in qualsiasi momento in cui *column* è stato definito con **srv_describe** e prima che sia stata inviata l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="21d23-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21d23-122">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="21d23-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="21d23-123">Per informazioni sui test e sull'analisi della sicurezza, visitare questo [sito Web Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="21d23-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d23-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21d23-124">See Also</span></span>  
 [<span data-ttu-id="21d23-125">srv_describe &#40;API Stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="21d23-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
