---
title: Finestra di dialogo Imposta parametri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628788"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="62c7e-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="62c7e-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="62c7e-103">La finestra di dialogo **Imposta parametri** consente di associare un parametro nuovo o esistente a una proprietà di un'attività.</span><span class="sxs-lookup"><span data-stu-id="62c7e-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="62c7e-104">È possibile aprire la finestra di dialogo facendo clic con il pulsante destro del mouse su un'attività o sulla scheda Flusso di controllo in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)], quindi selezionando **Imposta parametri**.</span><span class="sxs-lookup"><span data-stu-id="62c7e-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="62c7e-105">Nell'elenco seguente vengono descritti gli elementi dell'interfaccia utente della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="62c7e-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="62c7e-106">Per altre informazioni sui parametri, vedere [Parametri di Integration Services &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="62c7e-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="62c7e-107">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="62c7e-107">UI element list</span></span>  
 <span data-ttu-id="62c7e-108">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="62c7e-108">**Property**</span></span>  
 <span data-ttu-id="62c7e-109">Selezionare la proprietà dell'attività che si desidera associare a un parametro.</span><span class="sxs-lookup"><span data-stu-id="62c7e-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="62c7e-110">Questo elenco viene popolato con tutte le proprietà che è possibile impostare come parametri.</span><span class="sxs-lookup"><span data-stu-id="62c7e-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="62c7e-111">**Usa parametro esistente**</span><span class="sxs-lookup"><span data-stu-id="62c7e-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="62c7e-112">Selezionare questa opzione per associare la proprietà dell'attività a un parametro esistente, quindi selezionare il parametro dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="62c7e-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="62c7e-113">**Non utilizzare il parametro**</span><span class="sxs-lookup"><span data-stu-id="62c7e-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="62c7e-114">Selezionare questa opzione per rimuovere un riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="62c7e-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="62c7e-115">Il parametro non viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="62c7e-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="62c7e-116">**Crea nuovo parametro**</span><span class="sxs-lookup"><span data-stu-id="62c7e-116">**Create new parameter**</span></span>  
 <span data-ttu-id="62c7e-117">Selezionare questa opzione per creare un nuovo parametro che si desidera associare alla proprietà dell'attività.</span><span class="sxs-lookup"><span data-stu-id="62c7e-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="62c7e-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="62c7e-118">**Name**</span></span>  
 <span data-ttu-id="62c7e-119">Specificare il nome del parametro che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="62c7e-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="62c7e-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="62c7e-120">**Description**</span></span>  
 <span data-ttu-id="62c7e-121">Specificare la descrizione per il parametro.</span><span class="sxs-lookup"><span data-stu-id="62c7e-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="62c7e-122">**Valore**</span><span class="sxs-lookup"><span data-stu-id="62c7e-122">**Value**</span></span>  
 <span data-ttu-id="62c7e-123">Specificare il valore predefinito per il parametro.</span><span class="sxs-lookup"><span data-stu-id="62c7e-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="62c7e-124">Definito anche valore predefinito per la progettazione, potrà essere sostituito in seguito in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="62c7e-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="62c7e-125">**Ambito**</span><span class="sxs-lookup"><span data-stu-id="62c7e-125">**Scope**</span></span>  
 <span data-ttu-id="62c7e-126">Specificare l'ambito del parametro selezionando l'opzione **Progetto** o **Pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="62c7e-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="62c7e-127">I parametri del progetto vengono utilizzati per fornire input esterno ricevuto dal progetto a uno o più pacchetti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="62c7e-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="62c7e-128">I parametri del pacchetto consentono di modificare l'esecuzione del pacchetto senza doverlo modificare e ridistribuire.</span><span class="sxs-lookup"><span data-stu-id="62c7e-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="62c7e-129">**Distinzione**</span><span class="sxs-lookup"><span data-stu-id="62c7e-129">**Sensitive**</span></span>  
 <span data-ttu-id="62c7e-130">Specificare se il parametro è sensibile selezionando o deselezionando la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="62c7e-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="62c7e-131">I valori di parametri sensibili sono crittografati nel catalogo e risultano NULL quando vengono visualizzati con Transact-SQL o con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="62c7e-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="62c7e-132">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="62c7e-132">**Required**</span></span>  
 <span data-ttu-id="62c7e-133">Specificare se il parametro richiede che un valore diverso dal valore predefinito per la progettazione venga specificato prima dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62c7e-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="62c7e-134">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="62c7e-134">UI element list</span></span>  
  
