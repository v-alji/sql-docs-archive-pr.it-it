---
title: Pagina nuovo report collegato (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635449"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="e77f4-102">Pagina Nuovo report collegato (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="e77f4-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="e77f4-103">La pagina Nuovo report collegato consente di creare un report collegato.</span><span class="sxs-lookup"><span data-stu-id="e77f4-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="e77f4-104">Un report collegato è un report con impostazioni e proprietà proprie, ma collegato alla definizione di un altro report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="e77f4-105">I report collegati sono utili per utilizzare un report di base con alcune variazioni per gruppi o utenti specifici, ad esempio un report che restituisca dati diversi in base a un codice internazionale specificato come parametro.</span><span class="sxs-lookup"><span data-stu-id="e77f4-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="e77f4-106">I report collegati vengono in genere creati da un report con parametri, se l'esigenza è quella di variare e quindi salvare valori di parametri diversi per ogni istanza del report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="e77f4-107">È comunque possibile creare un report collegato da qualsiasi report accessibile.</span><span class="sxs-lookup"><span data-stu-id="e77f4-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="e77f4-108">Un report collegato dispone di nome, descrizione, posizione, proprietà dei parametri, proprietà per l'esecuzione del report, proprietà della cronologia del report, autorizzazioni e sottoscrizioni propri.</span><span class="sxs-lookup"><span data-stu-id="e77f4-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="e77f4-109">Un report collegato deve tuttavia utilizzare le stesse proprietà dell'origine dati e lo stesso layout del report di base che fornisce la definizione del report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="e77f4-110">Spostamento</span><span class="sxs-lookup"><span data-stu-id="e77f4-110">Navigation</span></span>  
 <span data-ttu-id="e77f4-111">Utilizzare le procedure riportate di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e77f4-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="e77f4-112">Per aprire la pagina Nuovo report collegato dalla pagina Contenuto</span><span class="sxs-lookup"><span data-stu-id="e77f4-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="e77f4-113">Aprire Gestione report e individuare un report per il quale si desidera creare un report collegato.</span><span class="sxs-lookup"><span data-stu-id="e77f4-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="e77f4-114">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="e77f4-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e77f4-115">Nel menu a discesa fare clic su **Crea report collegato**.</span><span class="sxs-lookup"><span data-stu-id="e77f4-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="e77f4-116">Per aprire la pagina Nuovo report collegato dalla pagina delle proprietà Generale di un report</span><span class="sxs-lookup"><span data-stu-id="e77f4-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="e77f4-117">Aprire Gestione report e individuare un report per il quale si desidera creare un report collegato.</span><span class="sxs-lookup"><span data-stu-id="e77f4-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="e77f4-118">Passare con il puntatore del mouse sul report, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="e77f4-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e77f4-119">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="e77f4-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="e77f4-120">Verrà visualizzata la pagina delle proprietà Generale per il report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="e77f4-121">Nella barra degli strumenti dell'elemento fare clic su **Crea report collegato**.</span><span class="sxs-lookup"><span data-stu-id="e77f4-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e77f4-122">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e77f4-122">Options</span></span>  
 <span data-ttu-id="e77f4-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e77f4-123">**Name**</span></span>  
 <span data-ttu-id="e77f4-124">Specificare il nome del report collegato.</span><span class="sxs-lookup"><span data-stu-id="e77f4-124">Specify the name of the linked report.</span></span> <span data-ttu-id="e77f4-125">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="e77f4-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="e77f4-126">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="e77f4-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="e77f4-127">I caratteri ; ?</span><span class="sxs-lookup"><span data-stu-id="e77f4-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="e77f4-128">: \@ & = +, $/\* \< > | "o/quando si specifica un nome.</span><span class="sxs-lookup"><span data-stu-id="e77f4-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="e77f4-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e77f4-129">**Description**</span></span>  
 <span data-ttu-id="e77f4-130">Consente di digitare una descrizione del contenuto del report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-130">Type a description of the report contents.</span></span> <span data-ttu-id="e77f4-131">Questa descrizione viene visualizzata nella pagina Contenuto per gli utenti autorizzati ad accedere al report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="e77f4-132">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="e77f4-132">**Location**</span></span>  
 <span data-ttu-id="e77f4-133">Specificare il percorso della cartella in cui è disponibile il report.</span><span class="sxs-lookup"><span data-stu-id="e77f4-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="e77f4-134">Per impostazione predefinita, i report collegati vengono creati nella stessa cartella del report di base.</span><span class="sxs-lookup"><span data-stu-id="e77f4-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="e77f4-135">Fare clic su **Cambia percorso** per inserire il report collegato in una cartella diversa.</span><span class="sxs-lookup"><span data-stu-id="e77f4-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="e77f4-136">**OK**</span><span class="sxs-lookup"><span data-stu-id="e77f4-136">**OK**</span></span>  
 <span data-ttu-id="e77f4-137">Fare clic su **OK** per salvare le modifiche e tornare alla pagina delle proprietà generale del report di base.</span><span class="sxs-lookup"><span data-stu-id="e77f4-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77f4-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e77f4-138">See Also</span></span>  
 <span data-ttu-id="e77f4-139">[Creazione di un report collegato](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="e77f4-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="e77f4-140">[Pagina delle proprietà generale, report &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e77f4-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="e77f4-141">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="e77f4-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
