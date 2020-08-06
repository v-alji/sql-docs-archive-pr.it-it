---
title: Editor trasformazione controllo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724056"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="2188b-102">Editor trasformazione Controllo</span><span class="sxs-lookup"><span data-stu-id="2188b-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="2188b-103">La trasformazione Controllo consente di includere nel flusso di dati di un pacchetto informazioni sull'ambiente in cui viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="2188b-104">Ad esempio, il nome del pacchetto, del computer e dell'operatore può essere aggiunto al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="2188b-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="2188b-105">include variabili di sistema che forniscono queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="2188b-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="2188b-106">Per ulteriori informazioni sulla trasformazione Controllo, vedere [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2188b-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2188b-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2188b-107">Options</span></span>  
 <span data-ttu-id="2188b-108">**Nome colonna di output**</span><span class="sxs-lookup"><span data-stu-id="2188b-108">**Output column name**</span></span>  
 <span data-ttu-id="2188b-109">Consente di specificare il nome di una nuova colonna di output che conterrà le informazioni di controllo.</span><span class="sxs-lookup"><span data-stu-id="2188b-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="2188b-110">**Tipo di controllo**</span><span class="sxs-lookup"><span data-stu-id="2188b-110">**Audit type**</span></span>  
 <span data-ttu-id="2188b-111">Consente di selezionare una variabile di sistema disponibile per visualizzare le informazioni di controllo.</span><span class="sxs-lookup"><span data-stu-id="2188b-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="2188b-112">Valore</span><span class="sxs-lookup"><span data-stu-id="2188b-112">Value</span></span>|<span data-ttu-id="2188b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2188b-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2188b-114">**GUID istanza esecuzione**</span><span class="sxs-lookup"><span data-stu-id="2188b-114">**Execution instance GUID**</span></span>|<span data-ttu-id="2188b-115">Consente di specificare il GUID che identifica in modo univoco l'istanza di esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="2188b-116">**ID pacchetto**</span><span class="sxs-lookup"><span data-stu-id="2188b-116">**Package ID**</span></span>|<span data-ttu-id="2188b-117">Consente di specificare il GUID che identifica in modo univoco il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="2188b-118">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="2188b-118">**Package name**</span></span>|<span data-ttu-id="2188b-119">Consente di specificare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-119">Insert the package name.</span></span>|  
|<span data-ttu-id="2188b-120">**ID versione**</span><span class="sxs-lookup"><span data-stu-id="2188b-120">**Version ID**</span></span>|<span data-ttu-id="2188b-121">Consente di specificare il GUID che identifica in modo univoco la versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="2188b-122">**Ora di inizio esecuzione**</span><span class="sxs-lookup"><span data-stu-id="2188b-122">**Execution start time**</span></span>|<span data-ttu-id="2188b-123">Consente di specificare l'ora di inizio dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="2188b-124">**Nome computer**</span><span class="sxs-lookup"><span data-stu-id="2188b-124">**Machine name**</span></span>|<span data-ttu-id="2188b-125">Consente di specificare il nome del computer sul quale è stato avviato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="2188b-126">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="2188b-126">**User name**</span></span>|<span data-ttu-id="2188b-127">Consente di specificare il nome dell'account di accesso dell'utente che ha avviato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2188b-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="2188b-128">**Nome attività**</span><span class="sxs-lookup"><span data-stu-id="2188b-128">**Task name**</span></span>|<span data-ttu-id="2188b-129">Consente di specificare il nome dell'attività Flusso di dati a cui è associata la trasformazione Controllo.</span><span class="sxs-lookup"><span data-stu-id="2188b-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="2188b-130">**ID attività**</span><span class="sxs-lookup"><span data-stu-id="2188b-130">**Task ID**</span></span>|<span data-ttu-id="2188b-131">Consente di specificare il GUID che identifica in modo univoco l'attività Flusso di dati a cui è associata la trasformazione Controllo.</span><span class="sxs-lookup"><span data-stu-id="2188b-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2188b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2188b-132">See Also</span></span>  
 [<span data-ttu-id="2188b-133">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="2188b-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
