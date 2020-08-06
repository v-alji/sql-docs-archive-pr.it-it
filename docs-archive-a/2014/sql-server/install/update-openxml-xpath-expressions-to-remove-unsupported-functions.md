---
title: Aggiornare le espressioni XPath OPENXML per rimuovere funzioni non supportate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628134"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="9d2a8-102">Aggiornare le espressioni XPath OPENXML in modo da rimuovere le funzioni non supportate</span><span class="sxs-lookup"><span data-stu-id="9d2a8-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="9d2a8-103">È stata rilevata la funzionalità XPath.</span><span class="sxs-lookup"><span data-stu-id="9d2a8-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="9d2a8-104">Dopo l'aggiornamento è possibile che le modifiche alla funzionalità XPath abbiano effetto per le funzionalità OPENXML.</span><span class="sxs-lookup"><span data-stu-id="9d2a8-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9d2a8-105">Componente</span><span class="sxs-lookup"><span data-stu-id="9d2a8-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9d2a8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d2a8-106">Description</span></span>  
 <span data-ttu-id="9d2a8-107">MSXML 3.0 è il motore sottostante utilizzato per l'elaborazione di espressioni XPath incluse in query OPENXML.</span><span class="sxs-lookup"><span data-stu-id="9d2a8-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="9d2a8-108">MSXML 3.0 include un motore XPath 1.0 più restrittivo che non supporta più le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d2a8-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="9d2a8-109">format-number()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-109">format-number()</span></span>  
  
-   <span data-ttu-id="9d2a8-110">formatNumber()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="9d2a8-111">current()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-111">current()</span></span>  
  
-   <span data-ttu-id="9d2a8-112">element-available()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-112">element-available()</span></span>  
  
-   <span data-ttu-id="9d2a8-113">function-available()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-113">function-available()</span></span>  
  
-   <span data-ttu-id="9d2a8-114">system-property()</span><span class="sxs-lookup"><span data-stu-id="9d2a8-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9d2a8-115">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="9d2a8-115">Corrective Action</span></span>  
 <span data-ttu-id="9d2a8-116">Nel caso di format-number() e formatNumber(), è possibile utilizzare [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d2a8-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9d2a8-117">Per le altre funzioni non supportate elencate in precedenza, non sono disponibili soluzioni alternative dirette.</span><span class="sxs-lookup"><span data-stu-id="9d2a8-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2a8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d2a8-118">See Also</span></span>  
 <span data-ttu-id="9d2a8-119">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9d2a8-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9d2a8-120">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="9d2a8-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
