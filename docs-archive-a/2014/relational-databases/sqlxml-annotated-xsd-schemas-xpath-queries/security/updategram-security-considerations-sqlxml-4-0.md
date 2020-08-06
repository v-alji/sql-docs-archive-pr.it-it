---
title: Considerazioni sulla sicurezza degli updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635984"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="f924b-102">Considerazioni sulla sicurezza degli updategram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f924b-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="f924b-103">Di seguito sono riportate alcune linee guida relative alla sicurezza quando si utilizzano gli updategram:</span><span class="sxs-lookup"><span data-stu-id="f924b-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="f924b-104">Evitare di utilizzare il mapping predefinito quando si utilizzano gli updategram per aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="f924b-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="f924b-105">Quando si utilizza il mapping predefinito, il nome di un elemento di un updategram esegue il mapping al nome di una tabella e il nome di un attributo esegue il mapping a una colonna.</span><span class="sxs-lookup"><span data-stu-id="f924b-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="f924b-106">In questo modo vengono esposte le informazioni sulle colonne e sulle tabelle di database. Ciò può costituire un potenziale rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f924b-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="f924b-107">Se invece si specifica uno schema di mapping separato che esegue il mapping degli elementi e degli attributi di un updategram alle tabelle e alle colonne di database, i nomi degli attributi e degli elementi dell'updategram possono essere arbitrari e lo schema esegue i mapping necessari di tali nomi alle tabelle e alle colonne di database.</span><span class="sxs-lookup"><span data-stu-id="f924b-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="f924b-108">Le informazioni del database non vengono pertanto esposte in un updategram.</span><span class="sxs-lookup"><span data-stu-id="f924b-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="f924b-109">Non consentire agli utenti di creare ed eseguire i relativi updategram.</span><span class="sxs-lookup"><span data-stu-id="f924b-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="f924b-110">È consigliabile che gli updategram vengano forniti come modelli in un server anziché essere creati dinamicamente in applicazioni di tipo ASP, situazione in cui i dati del database potrebbero essere a rischio.</span><span class="sxs-lookup"><span data-stu-id="f924b-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="f924b-111">Il potenziale rischio può essere eliminato consentendo agli utenti di accedere ai dati solo tramite gli updategram forniti come modelli.</span><span class="sxs-lookup"><span data-stu-id="f924b-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f924b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f924b-112">See Also</span></span>  
 [<span data-ttu-id="f924b-113">Utilizzo di updategram per modificare dati in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="f924b-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
