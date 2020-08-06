---
title: Finestra di dialogo Proprietà pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627347"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="9bad8-102">Finestra di dialogo Proprietà pacchetto</span><span class="sxs-lookup"><span data-stu-id="9bad8-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="9bad8-103">Utilizzare la finestra di dialogo **Proprietà pacchetto** per visualizzare le proprietà dei pacchetti archiviati nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9bad8-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="9bad8-104">Per altre informazioni, vedere [Server Integration Services &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="9bad8-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="9bad8-105">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="9bad8-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="9bad8-106">Aprire la finestra di dialogo Proprietà pacchetto</span><span class="sxs-lookup"><span data-stu-id="9bad8-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="9bad8-107">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="9bad8-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="9bad8-108">Aprire la finestra di dialogo Proprietà pacchetto</span><span class="sxs-lookup"><span data-stu-id="9bad8-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="9bad8-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9bad8-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="9bad8-110">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="9bad8-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="9bad8-111">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="9bad8-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="9bad8-112">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="9bad8-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="9bad8-113">Espandere la cartella che contiene il pacchetto di cui si desidera visualizzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="9bad8-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="9bad8-114">Fare clic con il pulsante destro del mouse sul pacchetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9bad8-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="9bad8-115">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="9bad8-115">Configure the Options</span></span>  
 <span data-ttu-id="9bad8-116">Utilizzare la pagina **Generale** per visualizzare le proprietà del pacchetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="9bad8-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="9bad8-117">Tutte le proprietà nella pagina **Generale** sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9bad8-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="9bad8-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9bad8-118">**Name**</span></span>  
 <span data-ttu-id="9bad8-119">Viene visualizzato il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9bad8-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="9bad8-120">**Identificatore**</span><span class="sxs-lookup"><span data-stu-id="9bad8-120">**Identifier**</span></span>  
 <span data-ttu-id="9bad8-121">Viene elencato l'ID del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9bad8-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="9bad8-122">**Punto di ingresso**</span><span class="sxs-lookup"><span data-stu-id="9bad8-122">**Entry Point**</span></span>  
 <span data-ttu-id="9bad8-123">Con il valore `True` viene indicato che il pacchetto viene avviato direttamente.</span><span class="sxs-lookup"><span data-stu-id="9bad8-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="9bad8-124">Con il valore `False` viene indicato che il pacchetto viene avviato da un altro pacchetto tramite l'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9bad8-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="9bad8-125">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="9bad8-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="9bad8-126">Questa proprietà si imposta in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] sia per il pacchetto padre che per i pacchetti figlio facendo clic con il pulsante destro del mouse sul pacchetto in Esplora soluzioni e selezionando **Pacchetto punto di ingresso**.</span><span class="sxs-lookup"><span data-stu-id="9bad8-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="9bad8-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9bad8-127">**Description**</span></span>  
 <span data-ttu-id="9bad8-128">Viene visualizzata la descrizione facoltativa del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9bad8-128">Displays the optional description of the package.</span></span>  
  
  
