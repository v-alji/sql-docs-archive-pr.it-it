---
title: Invio di set di risultati al server (API stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623278"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="fb2b4-102">Invio di set di risultati al server (API delle stored procedure estese)</span><span class="sxs-lookup"><span data-stu-id="fb2b4-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fb2b4-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="fb2b4-104">Quando si invia un set di risultati a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , il stored procedure esteso deve chiamare l'API appropriata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fb2b4-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="fb2b4-105">La funzione **srv_sendmsg** può essere chiamata in qualsiasi ordine prima o dopo l'invio di tutte le righe, se presenti, con **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="fb2b4-106">Tutti i messaggi devono essere inviati al client prima dell'invio dello stato di completamento con **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="fb2b4-107">La funzione **srv_sendrow** viene chiamata una volta per ogni riga inviata al client.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="fb2b4-108">Tutte le righe devono essere inviate al client prima dell'invio di qualsiasi messaggio, valore di stato o stato di completamento con **srv_sendmsg**, l'argomento **srv_status** di **srv_pfield**o **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="fb2b4-109">Quando si invia una riga in cui non sono state definite tutte le colonne con **srv_describe** , l'applicazione genera un messaggio di errore informativo e restituisce FAIL al client.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="fb2b4-110">In questo caso, la riga non viene inviata.</span><span class="sxs-lookup"><span data-stu-id="fb2b4-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2b4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb2b4-111">See Also</span></span>  
 [<span data-ttu-id="fb2b4-112">Creazione di stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="fb2b4-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
