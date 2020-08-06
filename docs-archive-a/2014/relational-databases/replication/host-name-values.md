---
title: Valori HOST_NAME | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624590"
---
# <a name="host_name-values"></a><span data-ttu-id="8444c-102">Valori HOST_NAME</span><span class="sxs-lookup"><span data-stu-id="8444c-102">HOST_NAME Values</span></span>
  <span data-ttu-id="8444c-103">Le pubblicazioni di tipo merge provviste di filtri con parametri utilizzano la funzione SUSER_SNAME() e/o HOST_NAME() per filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="8444c-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="8444c-104">La funzione viene specificata in Creazione guidata nuova pubblicazione oppure nella finestra di dialogo **Proprietà pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="8444c-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="8444c-105">Per impostazione predefinita, la funzione HOST_NAME() restituisce il nome del computer che esegue la connessione al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8444c-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="8444c-106">Se si utilizzano filtri con parametri, è possibile sostituire questo valore indicandone uno diverso in questa pagina della creazione guidata.</span><span class="sxs-lookup"><span data-stu-id="8444c-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="8444c-107">La funzione HOST_NAME() restituisce quindi il valore specificato anziché il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="8444c-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="8444c-108">Per altre informazioni, vedere la sezione "Sostituzione del valore di HOST_NAME()" nell'argomento [Filtri di riga con parametri](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8444c-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8444c-109">Se si sostituisce il valore HOST_NAME(), tutte le chiamate alla funzione HOST_NAME() restituiranno il valore specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8444c-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="8444c-110">Verificare che il funzionamento di altre applicazioni non dipenda dal fatto che HOST_NAME() restituisca il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="8444c-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8444c-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8444c-111">Options</span></span>  
 <span data-ttu-id="8444c-112">**Proprietà sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="8444c-112">**Subscription properties**</span></span>  
 <span data-ttu-id="8444c-113">Consente di specificare un valore per ogni Sottoscrittore nella colonna **Valore Host_NAME** . In alternativa, è possibile accettare il valore predefinito, ovvero il nome del computer Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="8444c-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8444c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8444c-114">See Also</span></span>  
 <span data-ttu-id="8444c-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="8444c-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="8444c-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="8444c-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="8444c-117">[Visualizzare e modificare le proprietà delle sottoscrizioni pull](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8444c-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="8444c-118">[Visualizzare e modificare le proprietà delle sottoscrizioni push](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8444c-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="8444c-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8444c-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="8444c-120">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="8444c-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
