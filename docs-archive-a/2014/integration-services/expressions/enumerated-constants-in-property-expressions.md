---
title: Costanti enumerate in espressioni di proprietà | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716543"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="bd655-102">Costanti enumerate in espressioni di proprietà</span><span class="sxs-lookup"><span data-stu-id="bd655-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="bd655-103">Nelle espressioni di proprietà che includono valori di un elenco di membri di un enumeratore è necessario utilizzare i valori numerici dei membri dell'enumeratore, anziché i relativi nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="bd655-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="bd655-104">In un'espressione che imposta la proprietà `LoggingMode`, ad esempio, è necessario utilizzare il valore numerico 2, anziché il nome descrittivo Disabled.</span><span class="sxs-lookup"><span data-stu-id="bd655-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="bd655-105">In questo argomento vengono elencati solo i valori numerici equivalenti ai nomi descrittivi degli enumeratori i cui membri vengono comunemente utilizzati nelle espressioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="bd655-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="bd655-106">Nel modello a oggetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sono inclusi numerosi enumeratori aggiuntivi che è possibile usare durante la programmazione del modello a oggetti per la compilazione di pacchetti a livello di programmazione o per la creazione di elementi di pacchetto con codice personalizzato, quali attività e componenti dei flussi di dati.</span><span class="sxs-lookup"><span data-stu-id="bd655-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="bd655-107">Oltre alle proprietà personalizzate dei pacchetti e degli oggetti di pacchetto, nella finestra Proprietà di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] è incluso un set di proprietà disponibili per pacchetti, attività e contenitori Ciclo Foreach, Ciclo For e Sequenza.</span><span class="sxs-lookup"><span data-stu-id="bd655-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="bd655-108">Le proprietà comuni impostate tramite valori di enumeratori,,, `ForceExecutionResult` `LoggingMode` e, `IsolationLevel` `Transaction Option` sono elencate nella sezione Proprietà comuni.</span><span class="sxs-lookup"><span data-stu-id="bd655-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="bd655-109">Nelle sezioni seguenti vengono fornite informazioni sulle costanti enumerate:</span><span class="sxs-lookup"><span data-stu-id="bd655-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="bd655-110">Pacchetto</span><span class="sxs-lookup"><span data-stu-id="bd655-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="bd655-111">Enumeratori per il ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="bd655-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="bd655-112">Attività</span><span class="sxs-lookup"><span data-stu-id="bd655-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="bd655-113">Attività Piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="bd655-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="bd655-114">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="bd655-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="bd655-115">Pacchetto</span><span class="sxs-lookup"><span data-stu-id="bd655-115">Package</span></span>  
 <span data-ttu-id="bd655-116">Nelle tabelle seguenti vengono elencati i nomi descrittivi e i valori numerici equivalenti per le proprietà dei pacchetti che è possibile impostare utilizzando i valori di un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="bd655-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="bd655-117">`PackageType`Set di proprietà utilizzando i valori dell' `DTSPackageType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-118">Nome descrittivo in DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="bd655-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="bd655-119">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-120">Predefinito</span><span class="sxs-lookup"><span data-stu-id="bd655-120">Default</span></span>|<span data-ttu-id="bd655-121">0</span><span class="sxs-lookup"><span data-stu-id="bd655-121">0</span></span>|  
|<span data-ttu-id="bd655-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="bd655-122">DTSWizard</span></span>|<span data-ttu-id="bd655-123">1</span><span class="sxs-lookup"><span data-stu-id="bd655-123">1</span></span>|  
|<span data-ttu-id="bd655-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="bd655-124">DTSDesigner</span></span>|<span data-ttu-id="bd655-125">2</span><span class="sxs-lookup"><span data-stu-id="bd655-125">2</span></span>|  
|<span data-ttu-id="bd655-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="bd655-126">SQLReplication</span></span>|<span data-ttu-id="bd655-127">3</span><span class="sxs-lookup"><span data-stu-id="bd655-127">3</span></span>|  
|<span data-ttu-id="bd655-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="bd655-128">DTSDesigner100</span></span>|<span data-ttu-id="bd655-129">5</span><span class="sxs-lookup"><span data-stu-id="bd655-129">5</span></span>|  
|<span data-ttu-id="bd655-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="bd655-130">SQLDBMaint</span></span>|<span data-ttu-id="bd655-131">6</span><span class="sxs-lookup"><span data-stu-id="bd655-131">6</span></span>|  
  
 <span data-ttu-id="bd655-132">`CheckpointUsage`Set di proprietà utilizzando i valori dell' `DTSCheckpointUsage` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-133">Nome descrittivo in DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="bd655-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="bd655-134">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-135">Never</span><span class="sxs-lookup"><span data-stu-id="bd655-135">Never</span></span>|<span data-ttu-id="bd655-136">0</span><span class="sxs-lookup"><span data-stu-id="bd655-136">0</span></span>|  
|<span data-ttu-id="bd655-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="bd655-137">IfExists</span></span>|<span data-ttu-id="bd655-138">1</span><span class="sxs-lookup"><span data-stu-id="bd655-138">1</span></span>|  
|<span data-ttu-id="bd655-139">Sempre</span><span class="sxs-lookup"><span data-stu-id="bd655-139">Always</span></span>|<span data-ttu-id="bd655-140">2</span><span class="sxs-lookup"><span data-stu-id="bd655-140">2</span></span>|  
  
 <span data-ttu-id="bd655-141">`PackagePriorityClass`Set di proprietà utilizzando i valori dell' `DTSPriorityClass` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-142">Nome descrittivo in DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="bd655-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="bd655-143">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="bd655-144">Predefinito</span><span class="sxs-lookup"><span data-stu-id="bd655-144">Default</span></span>|<span data-ttu-id="bd655-145">0</span><span class="sxs-lookup"><span data-stu-id="bd655-145">0</span></span>|  
|<span data-ttu-id="bd655-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="bd655-146">AboveNormal</span></span>|<span data-ttu-id="bd655-147">1</span><span class="sxs-lookup"><span data-stu-id="bd655-147">1</span></span>|  
|<span data-ttu-id="bd655-148">Normale</span><span class="sxs-lookup"><span data-stu-id="bd655-148">Normal</span></span>|<span data-ttu-id="bd655-149">2</span><span class="sxs-lookup"><span data-stu-id="bd655-149">2</span></span>|  
|<span data-ttu-id="bd655-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="bd655-150">BelowNormal</span></span>|<span data-ttu-id="bd655-151">3</span><span class="sxs-lookup"><span data-stu-id="bd655-151">3</span></span>|  
|<span data-ttu-id="bd655-152">Idle</span><span class="sxs-lookup"><span data-stu-id="bd655-152">Idle</span></span>|<span data-ttu-id="bd655-153">4</span><span class="sxs-lookup"><span data-stu-id="bd655-153">4</span></span>|  
  
 <span data-ttu-id="bd655-154">`ProtectionLevel`Set di proprietà utilizzando i valori dell' `DTSProtectionLevel` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-155">Nome descrittivo in DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="bd655-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="bd655-156">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="bd655-157">DontSaveSensitive</span></span>|<span data-ttu-id="bd655-158">0</span><span class="sxs-lookup"><span data-stu-id="bd655-158">0</span></span>|  
|<span data-ttu-id="bd655-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="bd655-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="bd655-160">1</span><span class="sxs-lookup"><span data-stu-id="bd655-160">1</span></span>|  
|<span data-ttu-id="bd655-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="bd655-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="bd655-162">2</span><span class="sxs-lookup"><span data-stu-id="bd655-162">2</span></span>|  
|<span data-ttu-id="bd655-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="bd655-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="bd655-164">3</span><span class="sxs-lookup"><span data-stu-id="bd655-164">3</span></span>|  
|<span data-ttu-id="bd655-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="bd655-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="bd655-166">4</span><span class="sxs-lookup"><span data-stu-id="bd655-166">4</span></span>|  
|<span data-ttu-id="bd655-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="bd655-167">ServerStorage</span></span>|<span data-ttu-id="bd655-168">5</span><span class="sxs-lookup"><span data-stu-id="bd655-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="bd655-169">Vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="bd655-169">Precedence Constraints</span></span>  
 <span data-ttu-id="bd655-170">`EvalOp`Set di proprietà utilizzando i valori dell' `DTSPrecedenceEvalOp` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-171">Nome descrittivo in DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="bd655-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="bd655-172">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-173">Expression</span><span class="sxs-lookup"><span data-stu-id="bd655-173">Expression</span></span>|<span data-ttu-id="bd655-174">1</span><span class="sxs-lookup"><span data-stu-id="bd655-174">1</span></span>|  
|<span data-ttu-id="bd655-175">Vincolo</span><span class="sxs-lookup"><span data-stu-id="bd655-175">Constraint</span></span>|<span data-ttu-id="bd655-176">2</span><span class="sxs-lookup"><span data-stu-id="bd655-176">2</span></span>|  
|<span data-ttu-id="bd655-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="bd655-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="bd655-178">3</span><span class="sxs-lookup"><span data-stu-id="bd655-178">3</span></span>|  
|<span data-ttu-id="bd655-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="bd655-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="bd655-180">4</span><span class="sxs-lookup"><span data-stu-id="bd655-180">4</span></span>|  
  
 <span data-ttu-id="bd655-181">`Value`Set di proprietà utilizzando i valori dell' `DTSExecResult` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-182">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="bd655-182">Friendly Name</span></span>|<span data-ttu-id="bd655-183">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="bd655-184">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="bd655-184">Success</span></span>|<span data-ttu-id="bd655-185">0</span><span class="sxs-lookup"><span data-stu-id="bd655-185">0</span></span>|  
|<span data-ttu-id="bd655-186">Operazioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="bd655-186">Failure</span></span>|<span data-ttu-id="bd655-187">1</span><span class="sxs-lookup"><span data-stu-id="bd655-187">1</span></span>|  
|<span data-ttu-id="bd655-188">Completion</span><span class="sxs-lookup"><span data-stu-id="bd655-188">Completion</span></span>|<span data-ttu-id="bd655-189">2</span><span class="sxs-lookup"><span data-stu-id="bd655-189">2</span></span>|  
|<span data-ttu-id="bd655-190">Cancellati</span><span class="sxs-lookup"><span data-stu-id="bd655-190">Canceled</span></span>|<span data-ttu-id="bd655-191">3</span><span class="sxs-lookup"><span data-stu-id="bd655-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="bd655-192">Enumeratori per il ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="bd655-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="bd655-193">Il ciclo Foreach include un set di enumeratori con proprietà che possono essere impostate tramite espressioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="bd655-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="bd655-194">Foreach ADO Enumerator</span><span class="sxs-lookup"><span data-stu-id="bd655-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="bd655-195">`Type`Set di proprietà utilizzando i valori dell' `ADOEnumerationType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-196">Nome descrittivo in ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="bd655-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="bd655-197">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="bd655-198">EnumerateTables</span></span>|<span data-ttu-id="bd655-199">0</span><span class="sxs-lookup"><span data-stu-id="bd655-199">0</span></span>|  
|<span data-ttu-id="bd655-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="bd655-200">EnumerateAllRows</span></span>|<span data-ttu-id="bd655-201">1</span><span class="sxs-lookup"><span data-stu-id="bd655-201">1</span></span>|  
|<span data-ttu-id="bd655-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="bd655-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="bd655-203">2</span><span class="sxs-lookup"><span data-stu-id="bd655-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="bd655-204">Enumeratore Foreach Nodelist</span><span class="sxs-lookup"><span data-stu-id="bd655-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="bd655-205">`SourceDocumentType``InnerXPathStringSourceType`proprietà, e **Proprietà OuterXPathStringSourceType** : impostate utilizzando i valori dell' `SourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-206">Nome descrittivo in SourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-206">Friendly name in SourceType</span></span>|<span data-ttu-id="bd655-207">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="bd655-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-208">FileConnection</span></span>|<span data-ttu-id="bd655-209">0</span><span class="sxs-lookup"><span data-stu-id="bd655-209">0</span></span>|  
|<span data-ttu-id="bd655-210">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-210">Variable</span></span>|<span data-ttu-id="bd655-211">1</span><span class="sxs-lookup"><span data-stu-id="bd655-211">1</span></span>|  
|<span data-ttu-id="bd655-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-212">DirectInput</span></span>|<span data-ttu-id="bd655-213">2</span><span class="sxs-lookup"><span data-stu-id="bd655-213">2</span></span>|  
  
 <span data-ttu-id="bd655-214">`EnumerationType`Set di proprietà utilizzando i valori dell' `EnumerationType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-215">Nome descrittivo in EnumerationType</span><span class="sxs-lookup"><span data-stu-id="bd655-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="bd655-216">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-217">Strumento di spostamento</span><span class="sxs-lookup"><span data-stu-id="bd655-217">Navigator</span></span>|<span data-ttu-id="bd655-218">0</span><span class="sxs-lookup"><span data-stu-id="bd655-218">0</span></span>|  
|<span data-ttu-id="bd655-219">Nodo</span><span class="sxs-lookup"><span data-stu-id="bd655-219">Node</span></span>|<span data-ttu-id="bd655-220">1</span><span class="sxs-lookup"><span data-stu-id="bd655-220">1</span></span>|  
|<span data-ttu-id="bd655-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="bd655-221">NodeText</span></span>|<span data-ttu-id="bd655-222">2</span><span class="sxs-lookup"><span data-stu-id="bd655-222">2</span></span>|  
|<span data-ttu-id="bd655-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="bd655-223">ElementCollection</span></span>|<span data-ttu-id="bd655-224">3</span><span class="sxs-lookup"><span data-stu-id="bd655-224">3</span></span>|  
  
 <span data-ttu-id="bd655-225">`InnerElementType`Set di proprietà utilizzando i valori dell' `InnerElementType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-226">Nome descrittivo in InnerElementType</span><span class="sxs-lookup"><span data-stu-id="bd655-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="bd655-227">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="bd655-228">Strumento di spostamento</span><span class="sxs-lookup"><span data-stu-id="bd655-228">Navigator</span></span>|<span data-ttu-id="bd655-229">0</span><span class="sxs-lookup"><span data-stu-id="bd655-229">0</span></span>|  
|<span data-ttu-id="bd655-230">Nodo</span><span class="sxs-lookup"><span data-stu-id="bd655-230">Node</span></span>|<span data-ttu-id="bd655-231">1</span><span class="sxs-lookup"><span data-stu-id="bd655-231">1</span></span>|  
|<span data-ttu-id="bd655-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="bd655-232">NodeText</span></span>|<span data-ttu-id="bd655-233">2</span><span class="sxs-lookup"><span data-stu-id="bd655-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="bd655-234">Attività</span><span class="sxs-lookup"><span data-stu-id="bd655-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="bd655-235">include numerose attività con proprietà che possono essere impostate tramite espressioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="bd655-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="bd655-236">Attività Esegui DDL Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bd655-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="bd655-237">`SourceType`Set di proprietà utilizzando i valori dell' `DDLSourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-238">Nome descrittivo in DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="bd655-239">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="bd655-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-240">DirectInput</span></span>|<span data-ttu-id="bd655-241">0</span><span class="sxs-lookup"><span data-stu-id="bd655-241">0</span></span>|  
|<span data-ttu-id="bd655-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-242">FileConnection</span></span>|<span data-ttu-id="bd655-243">1</span><span class="sxs-lookup"><span data-stu-id="bd655-243">1</span></span>|  
|<span data-ttu-id="bd655-244">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-244">Variable</span></span>|<span data-ttu-id="bd655-245">2</span><span class="sxs-lookup"><span data-stu-id="bd655-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="bd655-246">Inserimento bulk - attività</span><span class="sxs-lookup"><span data-stu-id="bd655-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="bd655-247">`DataFileType`Set di proprietà utilizzando i valori dell' `DTSBulkInsert_DataFileType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-248">Nome descrittivo in DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="bd655-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="bd655-249">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="bd655-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="bd655-251">0</span><span class="sxs-lookup"><span data-stu-id="bd655-251">0</span></span>|  
|<span data-ttu-id="bd655-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="bd655-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="bd655-253">1</span><span class="sxs-lookup"><span data-stu-id="bd655-253">1</span></span>|  
|<span data-ttu-id="bd655-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="bd655-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="bd655-255">2</span><span class="sxs-lookup"><span data-stu-id="bd655-255">2</span></span>|  
|<span data-ttu-id="bd655-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="bd655-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="bd655-257">3</span><span class="sxs-lookup"><span data-stu-id="bd655-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="bd655-258">Attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="bd655-258">Execute SQL Task</span></span>  
 <span data-ttu-id="bd655-259">`ResultSetType`Set di proprietà utilizzando i valori dell' `ResultSetType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-260">Nome descrittivo in ResultSetType</span><span class="sxs-lookup"><span data-stu-id="bd655-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="bd655-261">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="bd655-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="bd655-262">ResultSetType_None</span></span>|<span data-ttu-id="bd655-263">1</span><span class="sxs-lookup"><span data-stu-id="bd655-263">1</span></span>|  
|<span data-ttu-id="bd655-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="bd655-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="bd655-265">2</span><span class="sxs-lookup"><span data-stu-id="bd655-265">2</span></span>|  
|<span data-ttu-id="bd655-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="bd655-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="bd655-267">3</span><span class="sxs-lookup"><span data-stu-id="bd655-267">3</span></span>|  
|<span data-ttu-id="bd655-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="bd655-268">ResultSetType_XML</span></span>|<span data-ttu-id="bd655-269">4</span><span class="sxs-lookup"><span data-stu-id="bd655-269">4</span></span>|  
  
 <span data-ttu-id="bd655-270">`SqlStatementSourceType`Set di proprietà utilizzando i valori dell' `SqlStatementSourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-271">Nome descrittivo in SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="bd655-272">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-273">DirectInput</span></span>|<span data-ttu-id="bd655-274">1</span><span class="sxs-lookup"><span data-stu-id="bd655-274">1</span></span>|  
|<span data-ttu-id="bd655-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-275">FileConnection</span></span>|<span data-ttu-id="bd655-276">2</span><span class="sxs-lookup"><span data-stu-id="bd655-276">2</span></span>|  
|<span data-ttu-id="bd655-277">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-277">Variable</span></span>|<span data-ttu-id="bd655-278">3</span><span class="sxs-lookup"><span data-stu-id="bd655-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="bd655-279">Attività File system</span><span class="sxs-lookup"><span data-stu-id="bd655-279">File System Task</span></span>  
 <span data-ttu-id="bd655-280">`Operation`Set di proprietà utilizzando i valori dell' `DTSFileSystemOperation` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-281">Nome descrittivo in DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="bd655-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="bd655-282">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="bd655-283">CopyFile</span></span>|<span data-ttu-id="bd655-284">0</span><span class="sxs-lookup"><span data-stu-id="bd655-284">0</span></span>|  
|<span data-ttu-id="bd655-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="bd655-285">MoveFile</span></span>|<span data-ttu-id="bd655-286">1</span><span class="sxs-lookup"><span data-stu-id="bd655-286">1</span></span>|  
|<span data-ttu-id="bd655-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="bd655-287">DeleteFile</span></span>|<span data-ttu-id="bd655-288">2</span><span class="sxs-lookup"><span data-stu-id="bd655-288">2</span></span>|  
|<span data-ttu-id="bd655-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="bd655-289">RenameFile</span></span>|<span data-ttu-id="bd655-290">3</span><span class="sxs-lookup"><span data-stu-id="bd655-290">3</span></span>|  
|<span data-ttu-id="bd655-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="bd655-291">SetAttributes</span></span>|<span data-ttu-id="bd655-292">4</span><span class="sxs-lookup"><span data-stu-id="bd655-292">4</span></span>|  
|<span data-ttu-id="bd655-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="bd655-293">CreateDirectory</span></span>|<span data-ttu-id="bd655-294">5</span><span class="sxs-lookup"><span data-stu-id="bd655-294">5</span></span>|  
|<span data-ttu-id="bd655-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="bd655-295">CopyDirectory</span></span>|<span data-ttu-id="bd655-296">6</span><span class="sxs-lookup"><span data-stu-id="bd655-296">6</span></span>|  
|<span data-ttu-id="bd655-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="bd655-297">MoveDirectory</span></span>|<span data-ttu-id="bd655-298">7</span><span class="sxs-lookup"><span data-stu-id="bd655-298">7</span></span>|  
|<span data-ttu-id="bd655-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="bd655-299">DeleteDirectory</span></span>|<span data-ttu-id="bd655-300">8</span><span class="sxs-lookup"><span data-stu-id="bd655-300">8</span></span>|  
|<span data-ttu-id="bd655-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="bd655-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="bd655-302">9</span><span class="sxs-lookup"><span data-stu-id="bd655-302">9</span></span>|  
  
 <span data-ttu-id="bd655-303">`Attributes`Set di proprietà utilizzando i valori dell' `DTSFileSystemAttributes` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-304">Nome descrittivo in DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="bd655-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="bd655-305">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-306">Normale</span><span class="sxs-lookup"><span data-stu-id="bd655-306">Normal</span></span>|<span data-ttu-id="bd655-307">0</span><span class="sxs-lookup"><span data-stu-id="bd655-307">0</span></span>|  
|<span data-ttu-id="bd655-308">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="bd655-308">Archive</span></span>|<span data-ttu-id="bd655-309">1</span><span class="sxs-lookup"><span data-stu-id="bd655-309">1</span></span>|  
|<span data-ttu-id="bd655-310">Nascosto</span><span class="sxs-lookup"><span data-stu-id="bd655-310">Hidden</span></span>|<span data-ttu-id="bd655-311">2</span><span class="sxs-lookup"><span data-stu-id="bd655-311">2</span></span>|  
|<span data-ttu-id="bd655-312">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bd655-312">ReadOnly</span></span>|<span data-ttu-id="bd655-313">4</span><span class="sxs-lookup"><span data-stu-id="bd655-313">4</span></span>|  
|<span data-ttu-id="bd655-314">Sistema</span><span class="sxs-lookup"><span data-stu-id="bd655-314">System</span></span>|<span data-ttu-id="bd655-315">8</span><span class="sxs-lookup"><span data-stu-id="bd655-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="bd655-316">Attività FTP</span><span class="sxs-lookup"><span data-stu-id="bd655-316">FTP Task</span></span>  
 <span data-ttu-id="bd655-317">`Operation`Set di proprietà utilizzando i valori dell' `DTSFTPOp` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-318">Nome descrittivo in DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="bd655-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="bd655-319">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="bd655-320">Send</span><span class="sxs-lookup"><span data-stu-id="bd655-320">Send</span></span>|<span data-ttu-id="bd655-321">0</span><span class="sxs-lookup"><span data-stu-id="bd655-321">0</span></span>|  
|<span data-ttu-id="bd655-322">Ricevere</span><span class="sxs-lookup"><span data-stu-id="bd655-322">Receive</span></span>|<span data-ttu-id="bd655-323">1</span><span class="sxs-lookup"><span data-stu-id="bd655-323">1</span></span>|  
|<span data-ttu-id="bd655-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="bd655-324">DeleteLocal</span></span>|<span data-ttu-id="bd655-325">2</span><span class="sxs-lookup"><span data-stu-id="bd655-325">2</span></span>|  
|<span data-ttu-id="bd655-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="bd655-326">DeleteRemote</span></span>|<span data-ttu-id="bd655-327">3</span><span class="sxs-lookup"><span data-stu-id="bd655-327">3</span></span>|  
|<span data-ttu-id="bd655-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="bd655-328">MakeDirLocal</span></span>|<span data-ttu-id="bd655-329">4</span><span class="sxs-lookup"><span data-stu-id="bd655-329">4</span></span>|  
|<span data-ttu-id="bd655-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="bd655-330">MakeDirRemote</span></span>|<span data-ttu-id="bd655-331">5</span><span class="sxs-lookup"><span data-stu-id="bd655-331">5</span></span>|  
|<span data-ttu-id="bd655-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="bd655-332">RemoveDirLocal</span></span>|<span data-ttu-id="bd655-333">6</span><span class="sxs-lookup"><span data-stu-id="bd655-333">6</span></span>|  
|<span data-ttu-id="bd655-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="bd655-334">RemoveDirRemote</span></span>|<span data-ttu-id="bd655-335">7</span><span class="sxs-lookup"><span data-stu-id="bd655-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="bd655-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="bd655-336">Message Queue Task</span></span>  
 <span data-ttu-id="bd655-337">`MessageType`Set di proprietà utilizzando i valori dell' `MQMessageType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-338">Nome descrittivo in MQMessageType</span><span class="sxs-lookup"><span data-stu-id="bd655-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="bd655-339">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="bd655-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="bd655-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="bd655-341">0</span><span class="sxs-lookup"><span data-stu-id="bd655-341">0</span></span>|  
|<span data-ttu-id="bd655-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="bd655-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="bd655-343">1</span><span class="sxs-lookup"><span data-stu-id="bd655-343">1</span></span>|  
|<span data-ttu-id="bd655-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="bd655-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="bd655-345">2</span><span class="sxs-lookup"><span data-stu-id="bd655-345">2</span></span>|  
|<span data-ttu-id="bd655-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="bd655-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="bd655-347">3</span><span class="sxs-lookup"><span data-stu-id="bd655-347">3</span></span>|  
  
 <span data-ttu-id="bd655-348">`StringCompareType`Set di proprietà utilizzando i valori dell' `MQStringMessageCompare` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-349">Nome descrittivo in MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="bd655-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="bd655-350">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="bd655-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="bd655-352">0</span><span class="sxs-lookup"><span data-stu-id="bd655-352">0</span></span>|  
|<span data-ttu-id="bd655-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="bd655-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="bd655-354">1</span><span class="sxs-lookup"><span data-stu-id="bd655-354">1</span></span>|  
|<span data-ttu-id="bd655-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="bd655-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="bd655-356">2</span><span class="sxs-lookup"><span data-stu-id="bd655-356">2</span></span>|  
|<span data-ttu-id="bd655-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="bd655-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="bd655-358">3</span><span class="sxs-lookup"><span data-stu-id="bd655-358">3</span></span>|  
  
 <span data-ttu-id="bd655-359">`TaskType`Set di proprietà utilizzando i valori dell' `MQType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-360">Nome descrittivo in MQType</span><span class="sxs-lookup"><span data-stu-id="bd655-360">Friendly name in MQType</span></span>|<span data-ttu-id="bd655-361">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="bd655-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="bd655-362">DTSMQType_Sender</span></span>|<span data-ttu-id="bd655-363">0</span><span class="sxs-lookup"><span data-stu-id="bd655-363">0</span></span>|  
|<span data-ttu-id="bd655-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="bd655-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="bd655-365">1</span><span class="sxs-lookup"><span data-stu-id="bd655-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="bd655-366">Invia messaggi - attività</span><span class="sxs-lookup"><span data-stu-id="bd655-366">Send Mail Task</span></span>  
 <span data-ttu-id="bd655-367">`MessageSourceType`Set di proprietà utilizzando i valori dell' `SendMailMessageSourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-368">Nome descrittivo in SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="bd655-369">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-370">DirectInput</span></span>|<span data-ttu-id="bd655-371">0</span><span class="sxs-lookup"><span data-stu-id="bd655-371">0</span></span>|  
|<span data-ttu-id="bd655-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-372">FileConnection</span></span>|<span data-ttu-id="bd655-373">1</span><span class="sxs-lookup"><span data-stu-id="bd655-373">1</span></span>|  
|<span data-ttu-id="bd655-374">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-374">Variable</span></span>|<span data-ttu-id="bd655-375">2</span><span class="sxs-lookup"><span data-stu-id="bd655-375">2</span></span>|  
  
 <span data-ttu-id="bd655-376">`Priority`Set di proprietà utilizzando i valori dell' `MailPriority` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-377">Nome descrittivo in MailPriority</span><span class="sxs-lookup"><span data-stu-id="bd655-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="bd655-378">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="bd655-379">Alto</span><span class="sxs-lookup"><span data-stu-id="bd655-379">High</span></span>|<span data-ttu-id="bd655-380">1</span><span class="sxs-lookup"><span data-stu-id="bd655-380">1</span></span>|  
|<span data-ttu-id="bd655-381">Normale</span><span class="sxs-lookup"><span data-stu-id="bd655-381">Normal</span></span>|<span data-ttu-id="bd655-382">3</span><span class="sxs-lookup"><span data-stu-id="bd655-382">3</span></span>|  
|<span data-ttu-id="bd655-383">Basso</span><span class="sxs-lookup"><span data-stu-id="bd655-383">Low</span></span>|<span data-ttu-id="bd655-384">5</span><span class="sxs-lookup"><span data-stu-id="bd655-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="bd655-385">Attività Trasferisci database</span><span class="sxs-lookup"><span data-stu-id="bd655-385">Transfer Database Task</span></span>  
 <span data-ttu-id="bd655-386">`Action`Set di proprietà utilizzando i valori dell' `TransferAction` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-387">Nome descrittivo in TransferAction</span><span class="sxs-lookup"><span data-stu-id="bd655-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="bd655-388">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-389">Copiare</span><span class="sxs-lookup"><span data-stu-id="bd655-389">Copy</span></span>|<span data-ttu-id="bd655-390">0</span><span class="sxs-lookup"><span data-stu-id="bd655-390">0</span></span>|  
|<span data-ttu-id="bd655-391">Spostamento</span><span class="sxs-lookup"><span data-stu-id="bd655-391">Move</span></span>|<span data-ttu-id="bd655-392">1</span><span class="sxs-lookup"><span data-stu-id="bd655-392">1</span></span>|  
  
 <span data-ttu-id="bd655-393">`Method`Set di proprietà utilizzando i valori dell' `TransferMethod` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-394">Nome descrittivo in TransferMethod</span><span class="sxs-lookup"><span data-stu-id="bd655-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="bd655-395">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="bd655-396">DatabaseOffline</span></span>|<span data-ttu-id="bd655-397">0</span><span class="sxs-lookup"><span data-stu-id="bd655-397">0</span></span>|  
|<span data-ttu-id="bd655-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="bd655-398">DatabaseOnline</span></span>|<span data-ttu-id="bd655-399">1</span><span class="sxs-lookup"><span data-stu-id="bd655-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="bd655-400">Attività Trasferisci messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="bd655-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="bd655-401">`IfObjectExists`Set di proprietà utilizzando i valori dell' `IfObjectExists` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-402">Nome descrittivo in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="bd655-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="bd655-403">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="bd655-404">FailTask</span></span>|<span data-ttu-id="bd655-405">0</span><span class="sxs-lookup"><span data-stu-id="bd655-405">0</span></span>|  
|<span data-ttu-id="bd655-406">Overwrite</span><span class="sxs-lookup"><span data-stu-id="bd655-406">Overwrite</span></span>|<span data-ttu-id="bd655-407">1</span><span class="sxs-lookup"><span data-stu-id="bd655-407">1</span></span>|  
|<span data-ttu-id="bd655-408">Skip</span><span class="sxs-lookup"><span data-stu-id="bd655-408">Skip</span></span>|<span data-ttu-id="bd655-409">2</span><span class="sxs-lookup"><span data-stu-id="bd655-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="bd655-410">Attività Trasferisci processi</span><span class="sxs-lookup"><span data-stu-id="bd655-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="bd655-411">`IfObjectExists`Set di proprietà utilizzando i valori dell' `IfObjectExists` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-412">Nome descrittivo in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="bd655-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="bd655-413">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="bd655-414">FailTask</span></span>|<span data-ttu-id="bd655-415">0</span><span class="sxs-lookup"><span data-stu-id="bd655-415">0</span></span>|  
|<span data-ttu-id="bd655-416">Overwrite</span><span class="sxs-lookup"><span data-stu-id="bd655-416">Overwrite</span></span>|<span data-ttu-id="bd655-417">1</span><span class="sxs-lookup"><span data-stu-id="bd655-417">1</span></span>|  
|<span data-ttu-id="bd655-418">Skip</span><span class="sxs-lookup"><span data-stu-id="bd655-418">Skip</span></span>|<span data-ttu-id="bd655-419">2</span><span class="sxs-lookup"><span data-stu-id="bd655-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="bd655-420">Attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="bd655-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="bd655-421">`IfObjectExists`Set di proprietà utilizzando i valori dell' `IfObjectExists` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-422">Nome descrittivo in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="bd655-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="bd655-423">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="bd655-424">FailTask</span></span>|<span data-ttu-id="bd655-425">0</span><span class="sxs-lookup"><span data-stu-id="bd655-425">0</span></span>|  
|<span data-ttu-id="bd655-426">Overwrite</span><span class="sxs-lookup"><span data-stu-id="bd655-426">Overwrite</span></span>|<span data-ttu-id="bd655-427">1</span><span class="sxs-lookup"><span data-stu-id="bd655-427">1</span></span>|  
|<span data-ttu-id="bd655-428">Skip</span><span class="sxs-lookup"><span data-stu-id="bd655-428">Skip</span></span>|<span data-ttu-id="bd655-429">2</span><span class="sxs-lookup"><span data-stu-id="bd655-429">2</span></span>|  
  
 <span data-ttu-id="bd655-430">`LoginsToTransfer`Set di proprietà utilizzando i valori dell' `LoginsToTransfer` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-431">Nome descrittivo in LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="bd655-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="bd655-432">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="bd655-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="bd655-433">AllLogins</span></span>|<span data-ttu-id="bd655-434">0</span><span class="sxs-lookup"><span data-stu-id="bd655-434">0</span></span>|  
|<span data-ttu-id="bd655-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="bd655-435">SelectedLogins</span></span>|<span data-ttu-id="bd655-436">1</span><span class="sxs-lookup"><span data-stu-id="bd655-436">1</span></span>|  
|<span data-ttu-id="bd655-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="bd655-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="bd655-438">2</span><span class="sxs-lookup"><span data-stu-id="bd655-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="bd655-439">Attività Trasferisci stored procedure master</span><span class="sxs-lookup"><span data-stu-id="bd655-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="bd655-440">`IfObjectExists`Set di proprietà utilizzando i valori dell' `IfObjectExists` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-441">Nome descrittivo in IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="bd655-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="bd655-442">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="bd655-443">FailTask</span></span>|<span data-ttu-id="bd655-444">0</span><span class="sxs-lookup"><span data-stu-id="bd655-444">0</span></span>|  
|<span data-ttu-id="bd655-445">Overwrite</span><span class="sxs-lookup"><span data-stu-id="bd655-445">Overwrite</span></span>|<span data-ttu-id="bd655-446">1</span><span class="sxs-lookup"><span data-stu-id="bd655-446">1</span></span>|  
|<span data-ttu-id="bd655-447">Skip</span><span class="sxs-lookup"><span data-stu-id="bd655-447">Skip</span></span>|<span data-ttu-id="bd655-448">2</span><span class="sxs-lookup"><span data-stu-id="bd655-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="bd655-449">Attività Trasferisci oggetti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd655-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="bd655-450">`ExistingData`Set di proprietà utilizzando i valori dell' `ExistingData` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-451">Nome descrittivo in ExistingData</span><span class="sxs-lookup"><span data-stu-id="bd655-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="bd655-452">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="bd655-453">Replace</span><span class="sxs-lookup"><span data-stu-id="bd655-453">Replace</span></span>|<span data-ttu-id="bd655-454">0</span><span class="sxs-lookup"><span data-stu-id="bd655-454">0</span></span>|  
|<span data-ttu-id="bd655-455">Accoda</span><span class="sxs-lookup"><span data-stu-id="bd655-455">Append</span></span>|<span data-ttu-id="bd655-456">1</span><span class="sxs-lookup"><span data-stu-id="bd655-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="bd655-457">Attività Servizio Web</span><span class="sxs-lookup"><span data-stu-id="bd655-457">Web Service Task</span></span>  
 <span data-ttu-id="bd655-458">`OutputType`Set di proprietà utilizzando i valori dell' `DTSOutputType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-459">Nome descrittivo in DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="bd655-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="bd655-460">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="bd655-461">File</span><span class="sxs-lookup"><span data-stu-id="bd655-461">File</span></span>|<span data-ttu-id="bd655-462">0</span><span class="sxs-lookup"><span data-stu-id="bd655-462">0</span></span>|  
|<span data-ttu-id="bd655-463">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-463">Variable</span></span>|<span data-ttu-id="bd655-464">1</span><span class="sxs-lookup"><span data-stu-id="bd655-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="bd655-465">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="bd655-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="bd655-466">`OverwriteDestination`Set di proprietà utilizzando i valori dell' `OverwriteDestination` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-467">Nome descrittivo in OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="bd655-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="bd655-468">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="bd655-469">OverwriteDestination</span></span>|<span data-ttu-id="bd655-470">0</span><span class="sxs-lookup"><span data-stu-id="bd655-470">0</span></span>|  
|<span data-ttu-id="bd655-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="bd655-471">AppendToDestination</span></span>|<span data-ttu-id="bd655-472">1</span><span class="sxs-lookup"><span data-stu-id="bd655-472">1</span></span>|  
|<span data-ttu-id="bd655-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="bd655-473">KeepOriginal</span></span>|<span data-ttu-id="bd655-474">2</span><span class="sxs-lookup"><span data-stu-id="bd655-474">2</span></span>|  
  
 <span data-ttu-id="bd655-475">`OutputType`Set di proprietà utilizzando i valori dell' `OutputType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-476">Nome descrittivo in OutputType</span><span class="sxs-lookup"><span data-stu-id="bd655-476">Friendly name in OutputType</span></span>|<span data-ttu-id="bd655-477">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="bd655-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="bd655-478">DataTable</span></span>|<span data-ttu-id="bd655-479">0</span><span class="sxs-lookup"><span data-stu-id="bd655-479">0</span></span>|  
|<span data-ttu-id="bd655-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="bd655-480">PropertyValue</span></span>|<span data-ttu-id="bd655-481">1</span><span class="sxs-lookup"><span data-stu-id="bd655-481">1</span></span>|  
|<span data-ttu-id="bd655-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="bd655-482">PropertyNameAndValue</span></span>|<span data-ttu-id="bd655-483">2</span><span class="sxs-lookup"><span data-stu-id="bd655-483">2</span></span>|  
  
 <span data-ttu-id="bd655-484">`DestinationType`Set di proprietà utilizzando i valori dell' `DestinationType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-485">Nome descrittivo in DestinationType</span><span class="sxs-lookup"><span data-stu-id="bd655-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="bd655-486">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-487">FileConnection</span></span>|<span data-ttu-id="bd655-488">0</span><span class="sxs-lookup"><span data-stu-id="bd655-488">0</span></span>|  
|<span data-ttu-id="bd655-489">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-489">Variable</span></span>|<span data-ttu-id="bd655-490">1</span><span class="sxs-lookup"><span data-stu-id="bd655-490">1</span></span>|  
  
 <span data-ttu-id="bd655-491">`WqlQuerySourceType`Set di proprietà utilizzando i valori dell' `QuerySourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-492">Nome descrittivo in QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="bd655-493">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-494">FileConnection</span></span>|<span data-ttu-id="bd655-495">0</span><span class="sxs-lookup"><span data-stu-id="bd655-495">0</span></span>|  
|<span data-ttu-id="bd655-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-496">DirectInput</span></span>|<span data-ttu-id="bd655-497">1</span><span class="sxs-lookup"><span data-stu-id="bd655-497">1</span></span>|  
|<span data-ttu-id="bd655-498">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-498">Variable</span></span>|<span data-ttu-id="bd655-499">2</span><span class="sxs-lookup"><span data-stu-id="bd655-499">2</span></span>|  
  
 <span data-ttu-id="bd655-500">Proprietà di monitoraggio eventi WMI `ActionAtEvent` : impostata utilizzando i valori dell' `ActionAtEvent` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-501">Nome descrittivo in ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="bd655-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="bd655-502">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="bd655-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="bd655-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="bd655-504">0</span><span class="sxs-lookup"><span data-stu-id="bd655-504">0</span></span>|  
|<span data-ttu-id="bd655-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="bd655-505">LogTheEvent</span></span>|<span data-ttu-id="bd655-506">1</span><span class="sxs-lookup"><span data-stu-id="bd655-506">1</span></span>|  
  
 <span data-ttu-id="bd655-507">`ActionAtTimeout`Set di proprietà utilizzando i valori dell' `ActionAtTimeout` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-508">Nome descrittivo in ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="bd655-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="bd655-509">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="bd655-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="bd655-511">0</span><span class="sxs-lookup"><span data-stu-id="bd655-511">0</span></span>|  
|<span data-ttu-id="bd655-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="bd655-512">LogTimeout</span></span>|<span data-ttu-id="bd655-513">1</span><span class="sxs-lookup"><span data-stu-id="bd655-513">1</span></span>|  
  
 <span data-ttu-id="bd655-514">`AfterEvent`Set di proprietà utilizzando i valori dell' `AfterEvent` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-515">Nome descrittivo in AfterEvent</span><span class="sxs-lookup"><span data-stu-id="bd655-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="bd655-516">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="bd655-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="bd655-517">ReturnWithSuccess</span></span>|<span data-ttu-id="bd655-518">0</span><span class="sxs-lookup"><span data-stu-id="bd655-518">0</span></span>|  
|<span data-ttu-id="bd655-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="bd655-519">ReturnWithFailure</span></span>|<span data-ttu-id="bd655-520">1</span><span class="sxs-lookup"><span data-stu-id="bd655-520">1</span></span>|  
|<span data-ttu-id="bd655-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="bd655-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="bd655-522">2</span><span class="sxs-lookup"><span data-stu-id="bd655-522">2</span></span>|  
  
 <span data-ttu-id="bd655-523">`AfterTimeout`Set di proprietà utilizzando i valori dell' `AfterTimeout` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-524">Nome descrittivo in AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="bd655-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="bd655-525">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="bd655-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="bd655-526">ReturnWithSuccess</span></span>|<span data-ttu-id="bd655-527">0</span><span class="sxs-lookup"><span data-stu-id="bd655-527">0</span></span>|  
|<span data-ttu-id="bd655-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="bd655-528">ReturnWithFailure</span></span>|<span data-ttu-id="bd655-529">1</span><span class="sxs-lookup"><span data-stu-id="bd655-529">1</span></span>|  
|<span data-ttu-id="bd655-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="bd655-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="bd655-531">2</span><span class="sxs-lookup"><span data-stu-id="bd655-531">2</span></span>|  
  
 <span data-ttu-id="bd655-532">`WqlQuerySourceType`Set di proprietà utilizzando i valori dell' `QuerySourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-533">Nome descrittivo in QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="bd655-534">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-535">FileConnection</span></span>|<span data-ttu-id="bd655-536">0</span><span class="sxs-lookup"><span data-stu-id="bd655-536">0</span></span>|  
|<span data-ttu-id="bd655-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-537">DirectInput</span></span>|<span data-ttu-id="bd655-538">1</span><span class="sxs-lookup"><span data-stu-id="bd655-538">1</span></span>|  
|<span data-ttu-id="bd655-539">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-539">Variable</span></span>|<span data-ttu-id="bd655-540">2</span><span class="sxs-lookup"><span data-stu-id="bd655-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="bd655-541">Attività XML</span><span class="sxs-lookup"><span data-stu-id="bd655-541">XML Task</span></span>  
 <span data-ttu-id="bd655-542">`OperationType`Set di proprietà utilizzando i valori dell' `DTSXMLOperation` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-543">Nome descrittivo in DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="bd655-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="bd655-544">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-545">Convalida</span><span class="sxs-lookup"><span data-stu-id="bd655-545">Validate</span></span>|<span data-ttu-id="bd655-546">0</span><span class="sxs-lookup"><span data-stu-id="bd655-546">0</span></span>|  
|<span data-ttu-id="bd655-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="bd655-547">XSLT</span></span>|<span data-ttu-id="bd655-548">1</span><span class="sxs-lookup"><span data-stu-id="bd655-548">1</span></span>|  
|<span data-ttu-id="bd655-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="bd655-549">XPATH</span></span>|<span data-ttu-id="bd655-550">2</span><span class="sxs-lookup"><span data-stu-id="bd655-550">2</span></span>|  
|<span data-ttu-id="bd655-551">Unione</span><span class="sxs-lookup"><span data-stu-id="bd655-551">Merge</span></span>|<span data-ttu-id="bd655-552">3</span><span class="sxs-lookup"><span data-stu-id="bd655-552">3</span></span>|  
|<span data-ttu-id="bd655-553">Diff</span><span class="sxs-lookup"><span data-stu-id="bd655-553">Diff</span></span>|<span data-ttu-id="bd655-554">4</span><span class="sxs-lookup"><span data-stu-id="bd655-554">4</span></span>|  
|<span data-ttu-id="bd655-555">Patch</span><span class="sxs-lookup"><span data-stu-id="bd655-555">Patch</span></span>|<span data-ttu-id="bd655-556">5</span><span class="sxs-lookup"><span data-stu-id="bd655-556">5</span></span>|  
  
 <span data-ttu-id="bd655-557">`SourceType``SecondOperandType`proprietà, e `XPathSourceType` -impostate utilizzando i valori dell' `DTSXMLSourceType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-558">Nome descrittivo in DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="bd655-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="bd655-559">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="bd655-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-560">FileConnection</span></span>|<span data-ttu-id="bd655-561">0</span><span class="sxs-lookup"><span data-stu-id="bd655-561">0</span></span>|  
|<span data-ttu-id="bd655-562">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-562">Variable</span></span>|<span data-ttu-id="bd655-563">1</span><span class="sxs-lookup"><span data-stu-id="bd655-563">1</span></span>|  
|<span data-ttu-id="bd655-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="bd655-564">DirectInput</span></span>|<span data-ttu-id="bd655-565">2</span><span class="sxs-lookup"><span data-stu-id="bd655-565">2</span></span>|  
  
 <span data-ttu-id="bd655-566">`DestinationType`e proprietà **DiffGramDestinationType** -set usando i valori dell' `DTSXMLSaveResultTo` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-567">Nome descrittivo in DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="bd655-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="bd655-568">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="bd655-569">FileConnection</span></span>|<span data-ttu-id="bd655-570">0</span><span class="sxs-lookup"><span data-stu-id="bd655-570">0</span></span>|  
|<span data-ttu-id="bd655-571">Variabile</span><span class="sxs-lookup"><span data-stu-id="bd655-571">Variable</span></span>|<span data-ttu-id="bd655-572">1</span><span class="sxs-lookup"><span data-stu-id="bd655-572">1</span></span>|  
  
 <span data-ttu-id="bd655-573">`ValidationType`Set di proprietà utilizzando i valori dell' `DTSXMLValidationType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-574">Nome descrittivo in DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="bd655-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="bd655-575">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-576">DTD</span><span class="sxs-lookup"><span data-stu-id="bd655-576">DTD</span></span>|<span data-ttu-id="bd655-577">0</span><span class="sxs-lookup"><span data-stu-id="bd655-577">0</span></span>|  
|<span data-ttu-id="bd655-578">XSD</span><span class="sxs-lookup"><span data-stu-id="bd655-578">XSD</span></span>|<span data-ttu-id="bd655-579">1</span><span class="sxs-lookup"><span data-stu-id="bd655-579">1</span></span>|  
  
 <span data-ttu-id="bd655-580">`XPathOperation`Set di proprietà utilizzando i valori dell' `DTSXMLXPathOperation` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-581">Nome descrittivo in DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="bd655-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="bd655-582">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-583">Versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="bd655-583">Evaluation</span></span>|<span data-ttu-id="bd655-584">0</span><span class="sxs-lookup"><span data-stu-id="bd655-584">0</span></span>|  
|<span data-ttu-id="bd655-585">Valori</span><span class="sxs-lookup"><span data-stu-id="bd655-585">Values</span></span>|<span data-ttu-id="bd655-586">1</span><span class="sxs-lookup"><span data-stu-id="bd655-586">1</span></span>|  
|<span data-ttu-id="bd655-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="bd655-587">NodeList</span></span>|<span data-ttu-id="bd655-588">2</span><span class="sxs-lookup"><span data-stu-id="bd655-588">2</span></span>|  
  
 <span data-ttu-id="bd655-589">`DiffOptions`Set di proprietà utilizzando i valori dell' `DTSXMLDiffOptions` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="bd655-590">Le opzioni in questo enumeratore non si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="bd655-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="bd655-591">Per utilizzare più opzioni, specificare le opzioni desiderate in un elenco delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="bd655-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="bd655-592">Nome descrittivo in DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="bd655-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="bd655-593">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-594">nessuno</span><span class="sxs-lookup"><span data-stu-id="bd655-594">None</span></span>|<span data-ttu-id="bd655-595">0</span><span class="sxs-lookup"><span data-stu-id="bd655-595">0</span></span>|  
|<span data-ttu-id="bd655-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="bd655-596">IgnoreChildOrder</span></span>|<span data-ttu-id="bd655-597">1</span><span class="sxs-lookup"><span data-stu-id="bd655-597">1</span></span>|  
|<span data-ttu-id="bd655-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="bd655-598">IgnoreComments</span></span>|<span data-ttu-id="bd655-599">2</span><span class="sxs-lookup"><span data-stu-id="bd655-599">2</span></span>|  
|<span data-ttu-id="bd655-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="bd655-600">IgnorePI</span></span>|<span data-ttu-id="bd655-601">4</span><span class="sxs-lookup"><span data-stu-id="bd655-601">4</span></span>|  
|<span data-ttu-id="bd655-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="bd655-602">IgnoreWhitespace</span></span>|<span data-ttu-id="bd655-603">8</span><span class="sxs-lookup"><span data-stu-id="bd655-603">8</span></span>|  
|<span data-ttu-id="bd655-604">IgnoreNamespaces</span><span class="sxs-lookup"><span data-stu-id="bd655-604">IgnoreNamespaces</span></span>|<span data-ttu-id="bd655-605">16</span><span class="sxs-lookup"><span data-stu-id="bd655-605">16</span></span>|  
|<span data-ttu-id="bd655-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="bd655-606">IgnorePrefixes</span></span>|<span data-ttu-id="bd655-607">32</span><span class="sxs-lookup"><span data-stu-id="bd655-607">32</span></span>|  
|<span data-ttu-id="bd655-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="bd655-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="bd655-609">64</span><span class="sxs-lookup"><span data-stu-id="bd655-609">64</span></span>|  
|<span data-ttu-id="bd655-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="bd655-610">IgnoreDtd</span></span>|<span data-ttu-id="bd655-611">128</span><span class="sxs-lookup"><span data-stu-id="bd655-611">128</span></span>|  
  
 <span data-ttu-id="bd655-612">`DiffAlgorithm`Set di proprietà utilizzando i valori dell' `DTSXMLDiffAlgorithm` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-613">Nome descrittivo in DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="bd655-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="bd655-614">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-615">Auto</span><span class="sxs-lookup"><span data-stu-id="bd655-615">Auto</span></span>|<span data-ttu-id="bd655-616">0</span><span class="sxs-lookup"><span data-stu-id="bd655-616">0</span></span>|  
|<span data-ttu-id="bd655-617">Veloce</span><span class="sxs-lookup"><span data-stu-id="bd655-617">Fast</span></span>|<span data-ttu-id="bd655-618">1</span><span class="sxs-lookup"><span data-stu-id="bd655-618">1</span></span>|  
|<span data-ttu-id="bd655-619">Preciso</span><span class="sxs-lookup"><span data-stu-id="bd655-619">Precise</span></span>|<span data-ttu-id="bd655-620">2</span><span class="sxs-lookup"><span data-stu-id="bd655-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="bd655-621">Attività Piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="bd655-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="bd655-622">include un set di attività che consentono di eseguire attività di SQL Server da usare in piani di manutenzione e pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd655-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bd655-623">non supporta l'uso di queste attività a livello di codice e la documentazione di riferimento per la programmazione non include la documentazione dell'API di tali attività e dei relativi enumeratori.</span><span class="sxs-lookup"><span data-stu-id="bd655-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="bd655-624">Tutte le attività di manutenzione</span><span class="sxs-lookup"><span data-stu-id="bd655-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="bd655-625">Tutte le attività di manutenzione utilizzano le enumerazioni seguenti per impostare le proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="bd655-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="bd655-626">`DatabaseSelectionType`Set di proprietà utilizzando i valori dell' `DatabaseSelection` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-627">Nome descrittivo in DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="bd655-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="bd655-628">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="bd655-629">nessuno</span><span class="sxs-lookup"><span data-stu-id="bd655-629">None</span></span>|<span data-ttu-id="bd655-630">0</span><span class="sxs-lookup"><span data-stu-id="bd655-630">0</span></span>|  
|<span data-ttu-id="bd655-631">Tutti</span><span class="sxs-lookup"><span data-stu-id="bd655-631">All</span></span>|<span data-ttu-id="bd655-632">1</span><span class="sxs-lookup"><span data-stu-id="bd655-632">1</span></span>|  
|<span data-ttu-id="bd655-633">Sistema</span><span class="sxs-lookup"><span data-stu-id="bd655-633">System</span></span>|<span data-ttu-id="bd655-634">2</span><span class="sxs-lookup"><span data-stu-id="bd655-634">2</span></span>|  
|<span data-ttu-id="bd655-635">Utente</span><span class="sxs-lookup"><span data-stu-id="bd655-635">User</span></span>|<span data-ttu-id="bd655-636">3</span><span class="sxs-lookup"><span data-stu-id="bd655-636">3</span></span>|  
|<span data-ttu-id="bd655-637">Specifica</span><span class="sxs-lookup"><span data-stu-id="bd655-637">Specific</span></span>|<span data-ttu-id="bd655-638">4</span><span class="sxs-lookup"><span data-stu-id="bd655-638">4</span></span>|  
  
 <span data-ttu-id="bd655-639">`TableSelectionType`Set di proprietà utilizzando i valori dell' `TableSelection` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-640">Nome descrittivo in TableSelection</span><span class="sxs-lookup"><span data-stu-id="bd655-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="bd655-641">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-642">nessuno</span><span class="sxs-lookup"><span data-stu-id="bd655-642">None</span></span>|<span data-ttu-id="bd655-643">0</span><span class="sxs-lookup"><span data-stu-id="bd655-643">0</span></span>|  
|<span data-ttu-id="bd655-644">Tutti</span><span class="sxs-lookup"><span data-stu-id="bd655-644">All</span></span>|<span data-ttu-id="bd655-645">1</span><span class="sxs-lookup"><span data-stu-id="bd655-645">1</span></span>|  
|<span data-ttu-id="bd655-646">Specifica</span><span class="sxs-lookup"><span data-stu-id="bd655-646">Specific</span></span>|<span data-ttu-id="bd655-647">2</span><span class="sxs-lookup"><span data-stu-id="bd655-647">2</span></span>|  
  
 <span data-ttu-id="bd655-648">`ObjectTypeSelection`Set di proprietà utilizzando i valori dell' `ObjectType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-649">Nome descrittivo in ObjectType</span><span class="sxs-lookup"><span data-stu-id="bd655-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="bd655-650">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="bd655-651">Tabella</span><span class="sxs-lookup"><span data-stu-id="bd655-651">Table</span></span>|<span data-ttu-id="bd655-652">0</span><span class="sxs-lookup"><span data-stu-id="bd655-652">0</span></span>|  
|<span data-ttu-id="bd655-653">Visualizza</span><span class="sxs-lookup"><span data-stu-id="bd655-653">View</span></span>|<span data-ttu-id="bd655-654">1</span><span class="sxs-lookup"><span data-stu-id="bd655-654">1</span></span>|  
|<span data-ttu-id="bd655-655">TableView</span><span class="sxs-lookup"><span data-stu-id="bd655-655">TableView</span></span>|<span data-ttu-id="bd655-656">2</span><span class="sxs-lookup"><span data-stu-id="bd655-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="bd655-657">Attività Backup database</span><span class="sxs-lookup"><span data-stu-id="bd655-657">Back Up Database Task</span></span>  
 <span data-ttu-id="bd655-658">`DestinationCreationType`Set di proprietà utilizzando i valori dell' `DestinationType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-659">Nome descrittivo in DestinationType</span><span class="sxs-lookup"><span data-stu-id="bd655-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="bd655-660">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="bd655-661">Auto</span><span class="sxs-lookup"><span data-stu-id="bd655-661">Auto</span></span>|<span data-ttu-id="bd655-662">0</span><span class="sxs-lookup"><span data-stu-id="bd655-662">0</span></span>|  
|<span data-ttu-id="bd655-663">Manuale</span><span class="sxs-lookup"><span data-stu-id="bd655-663">Manual</span></span>|<span data-ttu-id="bd655-664">1</span><span class="sxs-lookup"><span data-stu-id="bd655-664">1</span></span>|  
  
 <span data-ttu-id="bd655-665">`ExistingBackupsAction`Set di proprietà utilizzando i valori dell' `ActionForExistingBackups` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-666">Nome descrittivo in ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="bd655-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="bd655-667">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-668">Accoda</span><span class="sxs-lookup"><span data-stu-id="bd655-668">Append</span></span>|<span data-ttu-id="bd655-669">0</span><span class="sxs-lookup"><span data-stu-id="bd655-669">0</span></span>|  
|<span data-ttu-id="bd655-670">Overwrite</span><span class="sxs-lookup"><span data-stu-id="bd655-670">Overwrite</span></span>|<span data-ttu-id="bd655-671">1</span><span class="sxs-lookup"><span data-stu-id="bd655-671">1</span></span>|  
  
 <span data-ttu-id="bd655-672">`BackupAction`Set di proprietà utilizzando i valori dell' `BackupTaskType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="bd655-673">Questa proprietà viene utilizzata insieme alla proprietà `BackupIsIncremental` per definire il tipo di backup eseguito dall'attività.</span><span class="sxs-lookup"><span data-stu-id="bd655-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="bd655-674">Nome descrittivo in BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="bd655-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="bd655-675">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-676">Database</span><span class="sxs-lookup"><span data-stu-id="bd655-676">Database</span></span>|<span data-ttu-id="bd655-677">0</span><span class="sxs-lookup"><span data-stu-id="bd655-677">0</span></span>|  
|<span data-ttu-id="bd655-678">File</span><span class="sxs-lookup"><span data-stu-id="bd655-678">Files</span></span>|<span data-ttu-id="bd655-679">1</span><span class="sxs-lookup"><span data-stu-id="bd655-679">1</span></span>|  
|<span data-ttu-id="bd655-680">File di log</span><span class="sxs-lookup"><span data-stu-id="bd655-680">Log</span></span>|<span data-ttu-id="bd655-681">2</span><span class="sxs-lookup"><span data-stu-id="bd655-681">2</span></span>|  
  
 <span data-ttu-id="bd655-682">`BackupDevice`Set di proprietà utilizzando i valori dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enumerazione SMO (Management Objects) `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="bd655-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-683">Nome descrittivo in DeviceType</span><span class="sxs-lookup"><span data-stu-id="bd655-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="bd655-684">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="bd655-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="bd655-685">LogicalDevice</span></span>|<span data-ttu-id="bd655-686">0</span><span class="sxs-lookup"><span data-stu-id="bd655-686">0</span></span>|  
|<span data-ttu-id="bd655-687">Nastro</span><span class="sxs-lookup"><span data-stu-id="bd655-687">Tape</span></span>|<span data-ttu-id="bd655-688">1</span><span class="sxs-lookup"><span data-stu-id="bd655-688">1</span></span>|  
|<span data-ttu-id="bd655-689">File</span><span class="sxs-lookup"><span data-stu-id="bd655-689">File</span></span>|<span data-ttu-id="bd655-690">2</span><span class="sxs-lookup"><span data-stu-id="bd655-690">2</span></span>|  
|<span data-ttu-id="bd655-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="bd655-691">Pipe</span></span>|<span data-ttu-id="bd655-692">3</span><span class="sxs-lookup"><span data-stu-id="bd655-692">3</span></span>|  
|<span data-ttu-id="bd655-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="bd655-693">VirtualDevice</span></span>|<span data-ttu-id="bd655-694">4</span><span class="sxs-lookup"><span data-stu-id="bd655-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="bd655-695">Pulizia file manutenzione - attività</span><span class="sxs-lookup"><span data-stu-id="bd655-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="bd655-696">`FileTypeSelected`Set di proprietà utilizzando i valori dell' `FileType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-697">Nome descrittivo in FileType</span><span class="sxs-lookup"><span data-stu-id="bd655-697">Friendly name in FileType</span></span>|<span data-ttu-id="bd655-698">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="bd655-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="bd655-699">FileBackup</span></span>|<span data-ttu-id="bd655-700">0</span><span class="sxs-lookup"><span data-stu-id="bd655-700">0</span></span>|  
|<span data-ttu-id="bd655-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="bd655-701">FileReport</span></span>|<span data-ttu-id="bd655-702">1</span><span class="sxs-lookup"><span data-stu-id="bd655-702">1</span></span>|  
  
 <span data-ttu-id="bd655-703">`OlderThanTimeUnitType`Set di proprietà utilizzando i valori dell' `TimeUnitType` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-704">Nome descrittivo in TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="bd655-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="bd655-705">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="bd655-706">Giorno</span><span class="sxs-lookup"><span data-stu-id="bd655-706">Day</span></span>|<span data-ttu-id="bd655-707">0</span><span class="sxs-lookup"><span data-stu-id="bd655-707">0</span></span>|  
|<span data-ttu-id="bd655-708">Week</span><span class="sxs-lookup"><span data-stu-id="bd655-708">Week</span></span>|<span data-ttu-id="bd655-709">1</span><span class="sxs-lookup"><span data-stu-id="bd655-709">1</span></span>|  
|<span data-ttu-id="bd655-710">Month</span><span class="sxs-lookup"><span data-stu-id="bd655-710">Month</span></span>|<span data-ttu-id="bd655-711">2</span><span class="sxs-lookup"><span data-stu-id="bd655-711">2</span></span>|  
|<span data-ttu-id="bd655-712">Year</span><span class="sxs-lookup"><span data-stu-id="bd655-712">Year</span></span>|<span data-ttu-id="bd655-713">3</span><span class="sxs-lookup"><span data-stu-id="bd655-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="bd655-714">Attività Aggiorna statistiche</span><span class="sxs-lookup"><span data-stu-id="bd655-714">Update Statistics Task</span></span>  
 <span data-ttu-id="bd655-715">`UpdateType`Set di proprietà utilizzando i valori dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enumerazione SMO (Management Objects) `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="bd655-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-716">Nome descrittivo in StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="bd655-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="bd655-717">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="bd655-718">Colonna</span><span class="sxs-lookup"><span data-stu-id="bd655-718">Column</span></span>|<span data-ttu-id="bd655-719">1</span><span class="sxs-lookup"><span data-stu-id="bd655-719">1</span></span>|  
|<span data-ttu-id="bd655-720">Indice</span><span class="sxs-lookup"><span data-stu-id="bd655-720">Index</span></span>|<span data-ttu-id="bd655-721">2</span><span class="sxs-lookup"><span data-stu-id="bd655-721">2</span></span>|  
|<span data-ttu-id="bd655-722">Tutti</span><span class="sxs-lookup"><span data-stu-id="bd655-722">All</span></span>|<span data-ttu-id="bd655-723">3</span><span class="sxs-lookup"><span data-stu-id="bd655-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="bd655-724">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="bd655-724">Common Properties</span></span>  
 <span data-ttu-id="bd655-725">I pacchetti, le attività e i contenitori Ciclo Foreach, Ciclo For e Sequenza possono utilizzare le enumerazioni seguenti per impostare le proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="bd655-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="bd655-726">`ForceExecutionResult`Set di proprietà utilizzando i valori dell' `DTSForcedExecResult` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-727">Nome descrittivo in DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="bd655-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="bd655-728">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-729">nessuno</span><span class="sxs-lookup"><span data-stu-id="bd655-729">None</span></span>|<span data-ttu-id="bd655-730">-1</span><span class="sxs-lookup"><span data-stu-id="bd655-730">-1</span></span>|  
|<span data-ttu-id="bd655-731">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="bd655-731">Success</span></span>|<span data-ttu-id="bd655-732">0</span><span class="sxs-lookup"><span data-stu-id="bd655-732">0</span></span>|  
|<span data-ttu-id="bd655-733">Operazioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="bd655-733">Failure</span></span>|<span data-ttu-id="bd655-734">1</span><span class="sxs-lookup"><span data-stu-id="bd655-734">1</span></span>|  
|<span data-ttu-id="bd655-735">Completion</span><span class="sxs-lookup"><span data-stu-id="bd655-735">Completion</span></span>|<span data-ttu-id="bd655-736">2</span><span class="sxs-lookup"><span data-stu-id="bd655-736">2</span></span>|  
  
 <span data-ttu-id="bd655-737">`IsolationLevel`Set di proprietà dall'enumerazione .NET Framework `IsolationLevel` .</span><span class="sxs-lookup"><span data-stu-id="bd655-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="bd655-738">Per altre informazioni, vedere la libreria di classi di Microsoft .NET Framework in [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="bd655-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="bd655-739">`LoggingMode`Set di proprietà utilizzando i valori dell' `DTSLoggingMode` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-740">Nome descrittivo in DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="bd655-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="bd655-741">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="bd655-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="bd655-742">UseParentSetting</span></span>|<span data-ttu-id="bd655-743">0</span><span class="sxs-lookup"><span data-stu-id="bd655-743">0</span></span>|  
|<span data-ttu-id="bd655-744">Attivato</span><span class="sxs-lookup"><span data-stu-id="bd655-744">Enabled</span></span>|<span data-ttu-id="bd655-745">1</span><span class="sxs-lookup"><span data-stu-id="bd655-745">1</span></span>|  
|<span data-ttu-id="bd655-746">Disabled</span><span class="sxs-lookup"><span data-stu-id="bd655-746">Disabled</span></span>|<span data-ttu-id="bd655-747">2</span><span class="sxs-lookup"><span data-stu-id="bd655-747">2</span></span>|  
  
 <span data-ttu-id="bd655-748">`TransactionOption`Set di proprietà utilizzando i valori dell' `DTSTransactionOption` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd655-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="bd655-749">Nome descrittivo in DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="bd655-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="bd655-750">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="bd655-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="bd655-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="bd655-751">NotSupported</span></span>|<span data-ttu-id="bd655-752">0</span><span class="sxs-lookup"><span data-stu-id="bd655-752">0</span></span>|  
|<span data-ttu-id="bd655-753">Supportato</span><span class="sxs-lookup"><span data-stu-id="bd655-753">Supported</span></span>|<span data-ttu-id="bd655-754">1</span><span class="sxs-lookup"><span data-stu-id="bd655-754">1</span></span>|  
|<span data-ttu-id="bd655-755">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="bd655-755">Required</span></span>|<span data-ttu-id="bd655-756">2</span><span class="sxs-lookup"><span data-stu-id="bd655-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="bd655-757">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="bd655-757">Related Tasks</span></span>  
 [<span data-ttu-id="bd655-758">Aggiungere o modificare un'espressione di proprietà</span><span class="sxs-lookup"><span data-stu-id="bd655-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd655-759">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd655-759">See Also</span></span>  
 <span data-ttu-id="bd655-760">[Utilizzo delle espressioni di proprietà nei pacchetti](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="bd655-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="bd655-761">[Pacchetti di Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="bd655-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="bd655-762">[Contenitori in Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="bd655-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="bd655-763">[Attività di Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="bd655-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="bd655-764">Vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="bd655-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
