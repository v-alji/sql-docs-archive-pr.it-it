---
title: Progettazione di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715840"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="154f0-102">Progettazione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="154f0-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="154f0-103">Sia il modello a oggetti amministrativo AMO (Analysis Management Objects) sia il modello a oggetti orientato al client [!INCLUDE[msCoName](../../includes/msconame-md.md)] ADO MD (ActiveX® Data Objects Multidimensional) sono disponibili nelle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="154f0-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="154f0-104">Le stored procedure devono essere in un determinato ambito (il server o il database) per essere visibili nel livello MDX (Multidimensional Expressions) e quindi essere chiamate.</span><span class="sxs-lookup"><span data-stu-id="154f0-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="154f0-105">Tuttavia, dopo che una stored procedure viene chiamata, il suo ambito non viene limitato alle azioni consentite dal relativo padre.</span><span class="sxs-lookup"><span data-stu-id="154f0-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="154f0-106">Una stored procedure può infatti apportare cambiamenti o modifiche in qualsiasi punto del server ed è soggetta solo a limitazioni di sicurezza del processo utente che l'ha richiamata o a limitazioni alla transazione nella quale è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="154f0-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="154f0-107">Le procedure nell'ambito del server sono disponibili in tutti i contesti del server.</span><span class="sxs-lookup"><span data-stu-id="154f0-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="154f0-108">Le stored procedure nell'ambito del database sono visibili solo nel contesto del database nel quale sono state definite.</span><span class="sxs-lookup"><span data-stu-id="154f0-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="154f0-109">Come qualsiasi altra funzione MDX, una stored procedure deve essere risolta prima che possa proseguire una sessione MDX. Le stored procedure bloccano le sessioni MDX durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="154f0-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="154f0-110">A meno che non esista una ragione specifica per interrompere una sessione MDX con una interazione con l'utente in corso, è consigliabile evitare interazioni con l'utente, quali ad esempio le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="154f0-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="154f0-111">Assembly dipendenti</span><span class="sxs-lookup"><span data-stu-id="154f0-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="154f0-112">Affinché il CLR (Common Language Runtime) trovi tutti gli assembly dipendenti, questi devono essere caricati in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="154f0-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="154f0-113">archivia gli assembly dipendenti nella stessa cartella dell'assembly principale, pertanto CLR risolve automaticamente ogni riferimento alla funzione in tali assembly.</span><span class="sxs-lookup"><span data-stu-id="154f0-113">stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154f0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="154f0-114">See Also</span></span>  
 <span data-ttu-id="154f0-115">[Gestione di assembly di modelli multidimensionali](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="154f0-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="154f0-116">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="154f0-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
