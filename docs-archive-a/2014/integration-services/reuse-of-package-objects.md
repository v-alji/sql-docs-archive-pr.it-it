---
title: Riutilizzo di oggetti di pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713267"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="99a7b-102">Riutilizzo di oggetti di pacchetto</span><span class="sxs-lookup"><span data-stu-id="99a7b-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="99a7b-103">Viene compressa frequentemente la funzionalità che si desidera riutilizzare.</span><span class="sxs-lookup"><span data-stu-id="99a7b-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="99a7b-104">Se, ad esempio, è stato creato un set di attività, potrebbe essere necessario riutilizzare questi elementi insieme, come gruppo, oppure riutilizzare singoli elementi quali una gestione connessione creata in un altro progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99a7b-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="99a7b-105">Copiare e incollare</span><span class="sxs-lookup"><span data-stu-id="99a7b-105">Copy and Paste</span></span>  
 <span data-ttu-id="99a7b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] è possibile copiare e incollare oggetti di pacchetto, in cui possono essere inclusi elementi di un flusso di controllo, elementi di un flusso di dati e gestioni connessioni.</span><span class="sxs-lookup"><span data-stu-id="99a7b-106">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="99a7b-107">È possibile copiare e incollare elementi sia tra progetti che tra pacchetti.</span><span class="sxs-lookup"><span data-stu-id="99a7b-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="99a7b-108">Se la soluzione contiene più progetti, è possibile copiare elementi tra i vari progetti, che possono anche essere di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="99a7b-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="99a7b-109">Se una soluzione contiene più pacchetti, sarà possibile copiare e incollare elementi tra i vari pacchetti,</span><span class="sxs-lookup"><span data-stu-id="99a7b-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="99a7b-110">che possono appartenere a uno stesso progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o a progetti diversi.</span><span class="sxs-lookup"><span data-stu-id="99a7b-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="99a7b-111">Gli oggetti di pacchetto possono tuttavia avere dipendenze da altri oggetti, in assenza dei quali non sono validi.</span><span class="sxs-lookup"><span data-stu-id="99a7b-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="99a7b-112">Se ad esempio un'attività Esegui SQL utilizza una gestione connessione, per consentire l'esecuzione dell'attività sarà necessario copiare anche la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="99a7b-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="99a7b-113">Esistono inoltre oggetti di pacchetto per cui è necessario che il pacchetto di destinazione contenga già un determinato oggetto, senza il quale non è possibile incollare gli oggetti copiati.</span><span class="sxs-lookup"><span data-stu-id="99a7b-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="99a7b-114">Non è ad esempio possibile incollare un flusso di dati in un pacchetto che non include almeno un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="99a7b-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="99a7b-115">Se si nota che alcuni pacchetti vengono copiati di frequente,</span><span class="sxs-lookup"><span data-stu-id="99a7b-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="99a7b-116">sarà possibile impostarli come modelli da utilizzare per la creazione di nuovi pacchetti, evitando così di copiarli ogni volta.</span><span class="sxs-lookup"><span data-stu-id="99a7b-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="99a7b-117">Quando si copia un oggetto di pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provvede automaticamente ad assegnare un nuovo GUID alla proprietà `ID` del nuovo oggetto e ad aggiornare la proprietà `Name`.</span><span class="sxs-lookup"><span data-stu-id="99a7b-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="99a7b-118">Non è possibile copiare variabili.</span><span class="sxs-lookup"><span data-stu-id="99a7b-118">You cannot copy variables.</span></span> <span data-ttu-id="99a7b-119">Se si copia un oggetto che utilizza variabili, ad esempio un'attività, sarà necessario ricreare le variabili nel pacchetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="99a7b-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="99a7b-120">Se invece si copia l'intero pacchetto, verranno copiate anche le variabili presenti nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="99a7b-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="99a7b-121">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="99a7b-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="99a7b-122">Copiare gli oggetti di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="99a7b-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="99a7b-123">Copia di elementi di progetto</span><span class="sxs-lookup"><span data-stu-id="99a7b-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="99a7b-124">Salvare un pacchetto come modello di pacchetto</span><span class="sxs-lookup"><span data-stu-id="99a7b-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
