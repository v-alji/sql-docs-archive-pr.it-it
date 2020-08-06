---
title: Transazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: 3b41e33a-c1ca-4b2a-9464-312b0ed3ca89
author: rothja
ms.author: jroth
ms.openlocfilehash: 1067820e80f9c7a4e1af2c8a14c85bc9dbfdd6aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636033"
---
# <a name="transactions"></a><span data-ttu-id="4bb62-102">Transazioni</span><span class="sxs-lookup"><span data-stu-id="4bb62-102">Transactions</span></span>
  <span data-ttu-id="4bb62-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa il supporto per le transazioni locali.</span><span class="sxs-lookup"><span data-stu-id="4bb62-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements local transaction support.</span></span> <span data-ttu-id="4bb62-104">Il consumer può utilizzare transazioni distribuite o coordinate tramite Microsoft Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="4bb62-104">The consumer can use distributed or coordinated transactions by using Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="4bb62-105">Per i consumer che richiedono il controllo delle transazioni che si estende su più sessioni, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può unire in join le transazioni avviate e gestite da MS DTC.</span><span class="sxs-lookup"><span data-stu-id="4bb62-105">For consumers requiring transaction control that spans multiple sessions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can join transactions initiated and maintained by MS DTC.</span></span>  
  
 <span data-ttu-id="4bb62-106">Per impostazione predefinita, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client utilizza una modalità di transazione con autocommit, in cui ogni azione discreta in una sessione del consumer comprende una transazione completa su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bb62-106">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider uses an autocommit transaction mode, where each discrete action on a consumer session comprises a complete transaction against an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bb62-107">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modalità autocommit del provider OLE DB di Native Client è locale e le transazioni autocommit non si estendono mai più di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="4bb62-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode is local, and autocommit transactions never span more than a single session.</span></span>  
  
 <span data-ttu-id="4bb62-108">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'interfaccia **ITransactionLocal** , consentendo al consumer di utilizzare in modo esplicito e implicito le transazioni di avvio in una singola connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bb62-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITransactionLocal** interface, allowing the consumer to use explicitly and implicitly start transactions on a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4bb62-109">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta le transazioni locali nidificate.</span><span class="sxs-lookup"><span data-stu-id="4bb62-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support nested local transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bb62-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4bb62-110">In This Section</span></span>  
  
-   [<span data-ttu-id="4bb62-111">Supporto delle transazioni locali</span><span class="sxs-lookup"><span data-stu-id="4bb62-111">Supporting Local Transactions</span></span>](supporting-local-transactions.md)  
  
-   [<span data-ttu-id="4bb62-112">Supporto di transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="4bb62-112">Supporting Distributed Transactions</span></span>](supporting-distributed-transactions.md)  
  
-   [<span data-ttu-id="4bb62-113">Livelli di isolamento &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4bb62-113">Isolation Levels &#40;OLE DB&#41;</span></span>](isolation-levels-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="4bb62-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bb62-114">See Also</span></span>  
 [<span data-ttu-id="4bb62-115">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4bb62-115">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
