---
title: Finestra di dialogo Proprietà origine dati, generale | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c79ad70cdd4dcb10e1abce1102fa39eef4c67461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623907"
---
# <a name="data-source-properties-dialog-box-general"></a><span data-ttu-id="41867-102">Finestra di dialogo Proprietà origine dati, Generale</span><span class="sxs-lookup"><span data-stu-id="41867-102">Data Source Properties Dialog Box, General</span></span>
  <span data-ttu-id="41867-103">Selezionare **Generale** nella finestra di dialogo **Proprietà origine dati** per visualizzare e modificare le informazioni di connessione per un'origine dati nel report.</span><span class="sxs-lookup"><span data-stu-id="41867-103">Select **General** on the **Data Source Properties** dialog box to display and modify connection information for a data source in the report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41867-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="41867-104">Options</span></span>  
 <span data-ttu-id="41867-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="41867-105">**Name**</span></span>  
 <span data-ttu-id="41867-106">Consente di digitare il nome dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="41867-106">Type the name of the data source.</span></span> <span data-ttu-id="41867-107">Tale nome deve essere univoco all'interno del report.</span><span class="sxs-lookup"><span data-stu-id="41867-107">The data source name must be unique within the report.</span></span> <span data-ttu-id="41867-108">Per impostazione predefinita, all'origine dei dati viene assegnato un nome generico, ad esempio DataSource1 o DataSource2.</span><span class="sxs-lookup"><span data-stu-id="41867-108">By default, a general name, such as DataSource1 or DataSource2, is assigned to the data source.</span></span>  
  
 <span data-ttu-id="41867-109">**Connessione incorporata**</span><span class="sxs-lookup"><span data-stu-id="41867-109">**Embedded connection**</span></span>  
 <span data-ttu-id="41867-110">Selezionare questa opzione se non si desidera utilizzare un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="41867-110">Select this option when you do not want to use a shared data source.</span></span>  
  
 <span data-ttu-id="41867-111">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41867-111">**Type**</span></span>  
 <span data-ttu-id="41867-112">Selezionare un'estensione per l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="41867-112">Select a data processing extension.</span></span> <span data-ttu-id="41867-113">Nell'elenco vengono visualizzate tutte le estensioni registrate.</span><span class="sxs-lookup"><span data-stu-id="41867-113">The list displays all registered extensions.</span></span>  
  
 <span data-ttu-id="41867-114">**Stringa di connessione**</span><span class="sxs-lookup"><span data-stu-id="41867-114">**Connection string**</span></span>  
 <span data-ttu-id="41867-115">Immettere una stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="41867-115">Enter a connection string for the data source.</span></span> <span data-ttu-id="41867-116">Fare clic su **Modifica** per compilare la stringa di connessione mediante la finestra di dialogo **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="41867-116">Click **Edit** to build the connection string using the **Connection Properties** dialog box.</span></span> <span data-ttu-id="41867-117">Fare clic sul pulsante **Espressioni** (*fx*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="41867-117">Click the **Expressions** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="41867-118">**Usa riferimento a origine dei dati condivisa**</span><span class="sxs-lookup"><span data-stu-id="41867-118">**Use shared data source reference**</span></span>  
 <span data-ttu-id="41867-119">Selezionare questa opzione per definire un collegamento a un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="41867-119">Select this option to link to a shared data source.</span></span> <span data-ttu-id="41867-120">Selezionare un'origine dati condivisa dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="41867-120">Select a shared data source from the drop-down list.</span></span> <span data-ttu-id="41867-121">Per modificare l'origine dati selezionata, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="41867-121">To edit the selected data source, click **Edit**.</span></span> <span data-ttu-id="41867-122">Se si seleziona **Usa riferimento a origine dei dati condivisa** , le opzioni **Tipo** e **Stringa di connessione** risulteranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="41867-122">If **Use shared data source reference** is selected, **Type** and **Connection string** are disabled.</span></span>  
  
 <span data-ttu-id="41867-123">**Usa transazione singola durante l'elaborazione delle query**</span><span class="sxs-lookup"><span data-stu-id="41867-123">**Use a single transaction when processing the queries**</span></span>  
 <span data-ttu-id="41867-124">Selezionare questa opzione per indicare che i set di dati che utilizzano l'origine dei dati vengono eseguiti in un'unica transazione sul database.</span><span class="sxs-lookup"><span data-stu-id="41867-124">Select this option to indicate that datasets that use this data source are run in a single transaction against the database.</span></span> <span data-ttu-id="41867-125">Per includere transazioni per sottoreport che utilizzano la stessa origine dati, impostare **MergeTransactions** su **True** nella sezione **Altro** del riquadro **Proprietà** del sottoreport.</span><span class="sxs-lookup"><span data-stu-id="41867-125">To include transactions for subreports that use the same data source, set **MergeTransactions** to **True** in the subreport's **Other** properties section of the **Properties** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41867-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41867-126">See Also</span></span>  
 <span data-ttu-id="41867-127">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41867-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="41867-128">[Creare un'origine dati incorporata o condivisa &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41867-128">[Create an Embedded or Shared Data Source &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="41867-129">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="41867-129">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="41867-130">Finestra di dialogo Proprietà origine dati, Credenziali</span><span class="sxs-lookup"><span data-stu-id="41867-130">Data Source Properties Dialog Box, Credentials</span></span>](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  
