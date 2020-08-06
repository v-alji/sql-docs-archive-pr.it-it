---
title: Tipi CLR definiti dall'utente di grandi dimensioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714275"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="0def1-102">Tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="0def1-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="0def1-103">In SQL Server 2005 i tipi definiti dall'utente in CLR (Common Language Runtime) sono limitati a dimensioni di 8.000 byte.</span><span class="sxs-lookup"><span data-stu-id="0def1-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="0def1-104">Questa restrizione è stata eliminata in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0def1-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="0def1-105">In questa versione i tipi CLR definiti dall'utente vengono considerati simili ai tipi LOB.</span><span class="sxs-lookup"><span data-stu-id="0def1-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="0def1-106">Tipi definiti dall'utente minori o uguali a 8.000 byte, pertanto, hanno lo stesso comportamento che in SQL Server 2005, ma sono supportati dati definiti dall'utente di dimensioni maggiori, che vengono indicate come illimitate ("unlimited").</span><span class="sxs-lookup"><span data-stu-id="0def1-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="0def1-107">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) e [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0def1-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="0def1-108">Casi d'uso</span><span class="sxs-lookup"><span data-stu-id="0def1-108">Use Cases</span></span>  
 <span data-ttu-id="0def1-109">Per ODBC, il supporto per i tipi definiti dall'utente di grandi dimensioni include la possibilità di inviare i valori di tali tipi in parti come parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="0def1-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="0def1-110">Questa operazione viene eseguita usando SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="0def1-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="0def1-111">Per OLE DB, il supporto per i tipi definiti dall'utente di grandi dimensioni include la possibilità di eseguire il flusso dei valori di tali tipi al e dal server usando l'associazione ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="0def1-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="0def1-112">Tipi definiti dall'utente minori o uguali a 8.000 byte hanno lo stesso comportamento che in SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="0def1-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="0def1-113">Per OLE DB, è comunque possibile trasmettere tipi definiti dall'utente di piccole dimensioni usando l'associazione ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="0def1-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="0def1-114">Il codice nativo dovrà talvolta riconoscere il contenuto dei tipi CLR definiti dall'utente, ma non dovrà creare istanze di oggetti gestiti.</span><span class="sxs-lookup"><span data-stu-id="0def1-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="0def1-115">In tal caso, è possibile utilizzare serializzazione personalizzata per convertire i valori dei tipi definiti dall'utente nel server in un formato noto per i client.</span><span class="sxs-lookup"><span data-stu-id="0def1-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="0def1-116">Per le applicazioni che dispongono di codice di accesso ai dati, è possibile sfruttare il comportamento dei tipi CLR definiti dall'utente nel client recuperando tali tipi tramite API native e creandone istanze tramite l'interoperabilità C++ CLI in applicazioni in modalità mista.</span><span class="sxs-lookup"><span data-stu-id="0def1-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0def1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0def1-117">See Also</span></span>  
 [<span data-ttu-id="0def1-118">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="0def1-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
