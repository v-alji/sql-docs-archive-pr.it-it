---
title: Modifiche al comportamento in syslockinfo e sp_lock | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628226"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="54c5e-102">Modifiche al comportamento in syslockinfo e sp_lock</span><span class="sxs-lookup"><span data-stu-id="54c5e-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="54c5e-103">**syslockinfo** e **sp_lock** possono restituire valori imprevisti.</span><span class="sxs-lookup"><span data-stu-id="54c5e-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="54c5e-104">Possono inoltre restituire righe aggiuntive, mentre le versioni precedenti di **syslockinfo** e **sp_lock** hanno restituito un massimo di due righe per ogni risorsa di blocco.</span><span class="sxs-lookup"><span data-stu-id="54c5e-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="54c5e-105">Per accedere alle informazioni da **syslockinfo** o Execute **sp_lock** è necessaria l'autorizzazione View Server state per il server.</span><span class="sxs-lookup"><span data-stu-id="54c5e-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="54c5e-106">Componente</span><span class="sxs-lookup"><span data-stu-id="54c5e-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="54c5e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54c5e-107">Description</span></span>  
 <span data-ttu-id="54c5e-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] le colonne **rsc_objid** e **rsc_indid** in **syslockinfo** e **objid** e le colonne **indid** in **sp_lock** restituiscono in modo coerente l'ID oggetto e l'ID dell'indice.</span><span class="sxs-lookup"><span data-stu-id="54c5e-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="54c5e-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] è possibile che venga restituito il valore 0.</span><span class="sxs-lookup"><span data-stu-id="54c5e-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="54c5e-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , **syslockinfo** e **sp_lock** restituiscono un massimo di due righe per ogni risorsa di blocco specificata in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="54c5e-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="54c5e-111">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], quando il partizionamento dei blocchi è abilitato, è possibile che vengano restituite più righe per la stessa risorsa eseguita in una transazione.</span><span class="sxs-lookup"><span data-stu-id="54c5e-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="54c5e-112">È possibile che vengano restituite fino a N + 1 righe, dove N è il numero di CPU.</span><span class="sxs-lookup"><span data-stu-id="54c5e-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="54c5e-113">È inoltre possibile che vengano visualizzate richieste GRANTED e WAITING per la stessa risorsa, il che non è possibile in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54c5e-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="54c5e-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="54c5e-114">Permissions</span></span>  
 <span data-ttu-id="54c5e-115">È richiesta l'autorizzazione VIEW SERVER STATE per il server.</span><span class="sxs-lookup"><span data-stu-id="54c5e-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c5e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54c5e-116">See Also</span></span>  
 <span data-ttu-id="54c5e-117">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="54c5e-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="54c5e-118">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="54c5e-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
