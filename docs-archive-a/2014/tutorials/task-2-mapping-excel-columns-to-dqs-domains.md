---
title: 'Attività 2: mapping delle colonne di Excel ai domini DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636498"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="6d50c-102">Attività 2: Mapping delle colonne di Excel ai domini DQS</span><span class="sxs-lookup"><span data-stu-id="6d50c-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="6d50c-103">Nella pagina **Mappa** selezionare **File di Excel** per **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="6d50c-104">Fare clic su **Sfoglia**, selezionare **Suppliers.xlsx**e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="6d50c-105">Selezionare **IncomingSuppliers $** per il **foglio di foglio**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="6d50c-106">Eseguire il mapping delle colonne come illustrato nella tabella e schermata seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d50c-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="6d50c-107">Quando si creano i mapping per il dominio di **stato** , fare clic sul pulsante **Aggiungi un mapping colonne** sulla barra degli strumenti posizionata sopra l'elenco.</span><span class="sxs-lookup"><span data-stu-id="6d50c-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="6d50c-108">Per la pulizia non si utilizza la colonna o il dominio **Supplier ID** .</span><span class="sxs-lookup"><span data-stu-id="6d50c-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="6d50c-109">Il dominio **Supplier ID** viene usato più avanti nell'attività di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6d50c-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="6d50c-110">Colonna di Excel</span><span class="sxs-lookup"><span data-stu-id="6d50c-110">Excel column</span></span>|<span data-ttu-id="6d50c-111">Dominio DQS</span><span class="sxs-lookup"><span data-stu-id="6d50c-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="6d50c-112">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="6d50c-112">Supplier Name</span></span>|<span data-ttu-id="6d50c-113">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="6d50c-113">Supplier Name</span></span>|  
    |<span data-ttu-id="6d50c-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="6d50c-114">ContactEmailAddress</span></span>|<span data-ttu-id="6d50c-115">Indirizzo di posta elettronica del contatto</span><span class="sxs-lookup"><span data-stu-id="6d50c-115">Contact Email</span></span>|  
    |<span data-ttu-id="6d50c-116">Riga indirizzo</span><span class="sxs-lookup"><span data-stu-id="6d50c-116">Address Line</span></span>|<span data-ttu-id="6d50c-117">Riga indirizzo</span><span class="sxs-lookup"><span data-stu-id="6d50c-117">Address Line</span></span>|  
    |<span data-ttu-id="6d50c-118">Città</span><span class="sxs-lookup"><span data-stu-id="6d50c-118">City</span></span>|<span data-ttu-id="6d50c-119">Città</span><span class="sxs-lookup"><span data-stu-id="6d50c-119">City</span></span>|  
    |<span data-ttu-id="6d50c-120">State</span><span class="sxs-lookup"><span data-stu-id="6d50c-120">State</span></span>|<span data-ttu-id="6d50c-121">State</span><span class="sxs-lookup"><span data-stu-id="6d50c-121">State</span></span>|  
    |<span data-ttu-id="6d50c-122">Country (fare clic su **+ (Aggiungi una colonna Mapping)** barra degli strumenti per aggiungere una riga</span><span class="sxs-lookup"><span data-stu-id="6d50c-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="6d50c-123">Paese</span><span class="sxs-lookup"><span data-stu-id="6d50c-123">Country</span></span>|  
    |<span data-ttu-id="6d50c-124">Zip Code</span><span class="sxs-lookup"><span data-stu-id="6d50c-124">Zip Code</span></span>|<span data-ttu-id="6d50c-125">Zip</span><span class="sxs-lookup"><span data-stu-id="6d50c-125">Zip</span></span>|  
  
     <span data-ttu-id="6d50c-126">![Mapping delle colonne di Excel ai domini](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mapping delle colonne di Excel ai domini")</span><span class="sxs-lookup"><span data-stu-id="6d50c-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="6d50c-127">Poiché è stato eseguito il mapping di tutti i singoli domini all'interno del dominio composito **Address Validation** , il dominio composito partecipa automaticamente al processo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="6d50c-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="6d50c-128">Fare clic sul pulsante **Visualizza/Seleziona domini compositi** per verificare che il dominio composito **Address Validation** sia selezionato automaticamente, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d50c-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6d50c-129">![Finestra di dialogo Visualizza/Seleziona domini compositi](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Finestra di dialogo Visualizza/Seleziona domini compositi")</span><span class="sxs-lookup"><span data-stu-id="6d50c-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="6d50c-130">Fare clic su **Avanti** per passare alla pagina **Pulisci** .</span><span class="sxs-lookup"><span data-stu-id="6d50c-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6d50c-131">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6d50c-131">Next Step</span></span>  
 [<span data-ttu-id="6d50c-132">Attività 3: Pulizia dei dati fornitore rispetto alla Knowledge Base Suppliers</span><span class="sxs-lookup"><span data-stu-id="6d50c-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
