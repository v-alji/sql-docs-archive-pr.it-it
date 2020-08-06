---
title: Trasformazione Controllo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712192"
---
# <a name="audit-transformation"></a><span data-ttu-id="b6b88-102">Controllo - trasformazione</span><span class="sxs-lookup"><span data-stu-id="b6b88-102">Audit Transformation</span></span>
  <span data-ttu-id="b6b88-103">La trasformazione Controllo consente di includere nel flusso di dati di un pacchetto informazioni sull'ambiente in cui viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="b6b88-104">Ad esempio, il nome del pacchetto, del computer e dell'operatore può essere aggiunto al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="b6b88-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="b6b88-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] include variabili di sistema che forniscono queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="b6b88-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="b6b88-106">Variabili di sistema</span><span class="sxs-lookup"><span data-stu-id="b6b88-106">System Variables</span></span>  
 <span data-ttu-id="b6b88-107">Nella tabella seguente sono descritte le variabili di sistema che possono essere utilizzate dalla trasformazione Controllo.</span><span class="sxs-lookup"><span data-stu-id="b6b88-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="b6b88-108">Variabile di sistema</span><span class="sxs-lookup"><span data-stu-id="b6b88-108">System variable</span></span>|<span data-ttu-id="b6b88-109">Indice</span><span class="sxs-lookup"><span data-stu-id="b6b88-109">Index</span></span>|<span data-ttu-id="b6b88-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b88-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="b6b88-111">0</span><span class="sxs-lookup"><span data-stu-id="b6b88-111">0</span></span>|<span data-ttu-id="b6b88-112">GUID che identifica l'istanza di esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="b6b88-113">1</span><span class="sxs-lookup"><span data-stu-id="b6b88-113">1</span></span>|<span data-ttu-id="b6b88-114">Identificatore univoco del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="b6b88-115">2</span><span class="sxs-lookup"><span data-stu-id="b6b88-115">2</span></span>|<span data-ttu-id="b6b88-116">Nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="b6b88-117">3</span><span class="sxs-lookup"><span data-stu-id="b6b88-117">3</span></span>|<span data-ttu-id="b6b88-118">Versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="b6b88-119">4</span><span class="sxs-lookup"><span data-stu-id="b6b88-119">4</span></span>|<span data-ttu-id="b6b88-120">Ora di inizio dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="b6b88-121">5</span><span class="sxs-lookup"><span data-stu-id="b6b88-121">5</span></span>|<span data-ttu-id="b6b88-122">Nome del computer.</span><span class="sxs-lookup"><span data-stu-id="b6b88-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="b6b88-123">6</span><span class="sxs-lookup"><span data-stu-id="b6b88-123">6</span></span>|<span data-ttu-id="b6b88-124">Nome dell'account di accesso dell'utente che ha avviato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6b88-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="b6b88-125">7</span><span class="sxs-lookup"><span data-stu-id="b6b88-125">7</span></span>|<span data-ttu-id="b6b88-126">Nome dell'attività Flusso di dati a cui è associata la trasformazione Controllo.</span><span class="sxs-lookup"><span data-stu-id="b6b88-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="b6b88-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="b6b88-127">**TaskId**</span></span>|<span data-ttu-id="b6b88-128">8</span><span class="sxs-lookup"><span data-stu-id="b6b88-128">8</span></span>|<span data-ttu-id="b6b88-129">Identificatore univoco dell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="b6b88-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="b6b88-130">Configurazione della trasformazione Controllo</span><span class="sxs-lookup"><span data-stu-id="b6b88-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="b6b88-131">Per configurare la trasformazione Controllo è necessario specificare il nome di una nuova colonna di output da aggiungere all'output della trasformazione ed eseguire il mapping della variabile di sistema a tale colonna di output.</span><span class="sxs-lookup"><span data-stu-id="b6b88-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="b6b88-132">È possibile eseguire il mapping di una stessa variabile di sistema a più colonne di output.</span><span class="sxs-lookup"><span data-stu-id="b6b88-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="b6b88-133">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="b6b88-133">This transformation has one input and one output.</span></span> <span data-ttu-id="b6b88-134">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="b6b88-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="b6b88-135">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="b6b88-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b6b88-136">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Controllo** , vedere [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b6b88-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="b6b88-137">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="b6b88-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b6b88-138">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6b88-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b6b88-139">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="b6b88-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b6b88-140">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="b6b88-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="b6b88-141">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b6b88-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
