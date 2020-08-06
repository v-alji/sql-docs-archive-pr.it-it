---
title: Programmazione di stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635607"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="8e89f-102">Programmazione di stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="8e89f-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8e89f-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="8e89f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8e89f-104">In passato i servizi ODS (Open Data Services) venivano utilizzati per scrivere applicazioni server, come gateway per ambienti di database non SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8e89f-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="8e89f-105">non [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporta le parti obsolete dell'API di Open Data Services.</span><span class="sxs-lookup"><span data-stu-id="8e89f-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="8e89f-106">Poiché l'unica parte dell'API di Open Data Services originale ancora supportata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è rappresentata dalle stored procedure estese, l'API è stata rinominata in API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="8e89f-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="8e89f-107">Con la comparsa delle più recenti e avanzate tecnologie, ad esempio le query distribuite e l'integrazione con CLR, la necessità di ricorrere alle applicazioni per l'API Stored procedure estesa è stata ampiamente soppiantata.</span><span class="sxs-lookup"><span data-stu-id="8e89f-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e89f-108">Se si dispone di applicazioni gateway esistenti, non è possibile utilizzare il file opends60.dll fornito con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8e89f-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="8e89f-109">Le applicazioni gateway non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="8e89f-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="8e89f-110">Confronto tra stored procedure estese e integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="8e89f-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="8e89f-111">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le stored procedure estese forniscono l'unico meccanismo a disposizione degli sviluppatori delle applicazioni di database per scrivere una logica sul lato server difficile da definire o impossibile da scrivere in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e89f-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8e89f-112">La funzionalità di integrazione con CLR offre un'alternativa più affidabile per la scrittura di tali stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8e89f-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="8e89f-113">Grazie all'integrazione con CLR, inoltre, la logica che veniva in genere scritta sotto forma di stored procedure viene spesso definita in modo anche più appropriato sotto forma di funzioni con valori di tabella. Tali funzioni consentono di eseguire query sui risultati restituiti nelle istruzioni SELECT incorporandoli nella clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="8e89f-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e89f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e89f-114">See Also</span></span>  
 <span data-ttu-id="8e89f-115">[Panoramica dell'integrazione di Common Language Runtime &#40;CLR&#41;](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8e89f-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="8e89f-116">Funzioni CLR con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="8e89f-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
