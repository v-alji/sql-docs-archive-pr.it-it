---
title: Configurare le dimensioni massime di caricamento file (PowerPivot per SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711059"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="f2b69-102">Configurare le dimensioni massime di caricamento dei file (PowerPivot per SharePoint)</span><span class="sxs-lookup"><span data-stu-id="f2b69-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="f2b69-103">Nelle cartelle di lavoro di PowerPivot sono spesso contenute grandi quantità di dati che comportano il superamento delle dimensioni massime del file consentite per i caricamenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f2b69-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="f2b69-104">Quando si tenta di caricare un file che supera il limite massimo, verrà visualizzato l'errore seguente in SharePoint:</span><span class="sxs-lookup"><span data-stu-id="f2b69-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="f2b69-105">"Le dimensioni del file specificato superano le dimensioni massime supportate".</span><span class="sxs-lookup"><span data-stu-id="f2b69-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="f2b69-106">Per aumentare le dimensioni del file, iniziare impostando l'opzione Dimensioni massime cartella di lavoro per Excel Services su 50 megabyte.</span><span class="sxs-lookup"><span data-stu-id="f2b69-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="f2b69-107">In questo modo, i limiti delle dimensioni massime del file per Excel vengono allineati a quelli delle applicazioni Web di SharePoint (impostati su 50 megabyte in SharePoint 2010 e su 200 in SharePoint 2013 per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="f2b69-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="f2b69-108">Se le dimensioni del file superano i 50 megabyte, aumentare i limiti delle dimensioni del file sia per Excel Services sia per l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="f2b69-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="f2b69-109">Per modificare le dimensioni massime di caricamento del file è necessario essere un amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f2b69-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="f2b69-110">Configurare le dimensioni massime del file per Excel Services</span><span class="sxs-lookup"><span data-stu-id="f2b69-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="f2b69-111">In Gestione applicazioni di Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="f2b69-112">Fare clic sul nome dell'applicazione Excel Services.</span><span class="sxs-lookup"><span data-stu-id="f2b69-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="f2b69-113">Fare clic su **Percorsi attendibili file**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="f2b69-114">Fare clic sulla posizione per modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="f2b69-114">Click the location to edit the properties.</span></span> <span data-ttu-id="f2b69-115">Per impostazione predefinita, in Excel Services l'applicazione Web predefinita viene considerata sito attendibile.</span><span class="sxs-lookup"><span data-stu-id="f2b69-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="f2b69-116">Se si usa l'applicazione Web predefinita, fare clic su **http://** per aprire la pagina di configurazione per questo percorso.</span><span class="sxs-lookup"><span data-stu-id="f2b69-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="f2b69-117">Scorrere fino a **Proprietà cartella di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="f2b69-118">In Dimensioni massime cartella di lavoro aumentare le dimensioni del file da 10 (valore predefinito) a 50 o a una dimensione maggiore, appropriata ai file in uso.</span><span class="sxs-lookup"><span data-stu-id="f2b69-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="f2b69-119">Per impostazione predefinita, 50 megabyte rappresenta la dimensione di caricamento file massima per le applicazioni Web di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f2b69-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="f2b69-120">Se l'opzione Dimensioni massime cartella di lavoro viene impostata su un valore maggiore di 50 megabyte, seguire i passaggi nella procedura descritta di seguito per aumentare Dimensioni massime caricamento per l'applicazione Web di SharePoint allo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="f2b69-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="f2b69-121">Il valore massimo che è possibile specificare è 2 gigabyte (o 2047 megabyte come specificato in Amministrazione centrale).</span><span class="sxs-lookup"><span data-stu-id="f2b69-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="f2b69-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="f2b69-123">Configurare le dimensioni massime del file per un'applicazione Web di SharePoint</span><span class="sxs-lookup"><span data-stu-id="f2b69-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="f2b69-124">In Gestione applicazioni di amministrazione centrale fare clic su **Gestisci applicazioni Web**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2b69-125">Effettuare i passaggi seguenti solo se è stato aumentato il valore dell'opzione Dimensioni massime cartella di lavoro in Excel Services.</span><span class="sxs-lookup"><span data-stu-id="f2b69-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="f2b69-126">Selezionare l'applicazione, ad esempio **SharePoint - 80**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="f2b69-127">Sulla barra multifunzione delle applicazioni Web, fare clic sulla freccia GIÙ sul pulsante Impostazioni generali.</span><span class="sxs-lookup"><span data-stu-id="f2b69-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="f2b69-128">Fare clic su **Impostazioni generali**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="f2b69-129">Scorrere fino a **Dimensioni massime caricamento**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="f2b69-130">Impostare la proprietà sul numero uguale o maggiore di quello impostato in Dimensioni massime cartella di lavoro in Excel Services.</span><span class="sxs-lookup"><span data-stu-id="f2b69-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="f2b69-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2b69-131">Click **OK**.</span></span>  
  
  
