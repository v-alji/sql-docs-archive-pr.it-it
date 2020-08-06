---
title: Livelli di isolamento (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629785"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="180f8-102">Livelli di isolamento (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="180f8-102">Isolation Levels (OLE DB)</span></span>
  <span data-ttu-id="180f8-103">I client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono controllare i livelli di isolamento delle transazioni per una connessione.</span><span class="sxs-lookup"><span data-stu-id="180f8-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="180f8-104">Per controllare il livello di isolamento delle transazioni, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider OLE DB di Native Client USA:</span><span class="sxs-lookup"><span data-stu-id="180f8-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="180f8-105">DBPROPSET_SESSION DBPROP_SESS_AUTOCOMMITISOLEVELS proprietà per la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modalità autocommit predefinita del provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="180f8-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="180f8-106">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valore predefinito del provider OLE DB di Native Client per il livello è DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="180f8-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="180f8-107">Parametro *isoLevel* del metodo **ITransactionLocal::StartTransaction** per le transazioni locali di cui viene eseguito il commit manuale.</span><span class="sxs-lookup"><span data-stu-id="180f8-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="180f8-108">Parametro *isoLevel* del metodo **ITransactionDispenser::BeginTransaction** per le transazioni distribuite coordinate da MS DTC.</span><span class="sxs-lookup"><span data-stu-id="180f8-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="180f8-109">consente accesso di sola lettura nel livello di isolamento di lettura dirty.</span><span class="sxs-lookup"><span data-stu-id="180f8-109">allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="180f8-110">Tutti gli altri livelli limitano la concorrenza applicando blocchi agli oggetti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="180f8-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="180f8-111">Poiché il client richiede livelli di concorrenza maggiori, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applica restrizioni superiori all'accesso simultaneo ai dati.</span><span class="sxs-lookup"><span data-stu-id="180f8-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="180f8-112">Per mantenere il livello più elevato di accesso simultaneo ai dati, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider di OLE DB di Native client deve controllare in modo intelligente le richieste di livelli di concorrenza specifici.</span><span class="sxs-lookup"><span data-stu-id="180f8-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="180f8-113">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] è stato introdotto il livello di isolamento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="180f8-113">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduced snapshot isolation level.</span></span> <span data-ttu-id="180f8-114">Per altre informazioni, vedere [Uso dell'isolamento dello snapshot](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="180f8-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180f8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="180f8-115">See Also</span></span>  
 [<span data-ttu-id="180f8-116">Transazioni</span><span class="sxs-lookup"><span data-stu-id="180f8-116">Transactions</span></span>](transactions.md)  
  
  
