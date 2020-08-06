---
title: Eseguire il mapping delle colonne ai domini compositi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636304"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="98e62-102">Eseguire il mapping delle colonne ai domini compositi</span><span class="sxs-lookup"><span data-stu-id="98e62-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="98e62-103">Un dominio composito è costituito da due o più singoli domini.</span><span class="sxs-lookup"><span data-stu-id="98e62-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="98e62-104">È possibile eseguire il mapping di più colonne oppure di una singola colonna con valori delimitati al dominio.</span><span class="sxs-lookup"><span data-stu-id="98e62-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="98e62-105">Se sono disponibili più colonne, è necessario eseguire il mapping di una colonna a ogni singolo dominio nel dominio composito per applicare le regole di quest'ultimo alla pulizia dati.</span><span class="sxs-lookup"><span data-stu-id="98e62-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="98e62-106">Selezionare i singoli domini inclusi nel dominio composito nel client Data Quality.</span><span class="sxs-lookup"><span data-stu-id="98e62-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="98e62-107">Per altre informazioni, vedere [Creazione di un dominio composito](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="98e62-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="98e62-108">Se è disponibile una singola colonna con valori delimitati, è necessario eseguire il mapping della singola colonna al dominio composito.</span><span class="sxs-lookup"><span data-stu-id="98e62-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="98e62-109">I valori devono essere visualizzati nello stesso ordine dei singoli domini nel dominio composito.</span><span class="sxs-lookup"><span data-stu-id="98e62-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="98e62-110">Il delimitatore nell'origine dati deve corrispondere al delimitatore utilizzato per analizzare i valori del dominio composito.</span><span class="sxs-lookup"><span data-stu-id="98e62-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="98e62-111">È possibile selezionare il delimitatore per il dominio composito, nonché impostare altre proprietà nel client Data Quality.</span><span class="sxs-lookup"><span data-stu-id="98e62-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="98e62-112">Per altre informazioni, vedere [Creazione di un dominio composito](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="98e62-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="98e62-113">Per eseguire il mapping di più colonne a un dominio composito</span><span class="sxs-lookup"><span data-stu-id="98e62-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="98e62-114">Fare clic con il pulsante destro del mouse sulla trasformazione DQS Cleansing e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="98e62-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="98e62-115">Nella scheda **Gestione connessione** verificare che il dominio composito sia visualizzato nell'elenco dei domini disponibili.</span><span class="sxs-lookup"><span data-stu-id="98e62-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="98e62-116">Nella scheda **Mapping** selezionare le colonne nell'area **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="98e62-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="98e62-117">Per ogni colonna elencata nel campo **Colonna di input** selezionare un singolo dominio nel campo **Dominio** .</span><span class="sxs-lookup"><span data-stu-id="98e62-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="98e62-118">Selezionare solo singoli domini disponibili nel dominio composito.</span><span class="sxs-lookup"><span data-stu-id="98e62-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="98e62-119">In base alle esigenze, modificare i nomi visualizzati nei campi **Alias di origine**, **Alias di output**e **Alias di stato** .</span><span class="sxs-lookup"><span data-stu-id="98e62-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="98e62-120">In base alle esigenze, impostare le proprietà nella scheda **Avanzate** . Per altre informazioni sulle proprietà, vedere [Finestra di dialogo Editor trasformazione DQS Cleansing](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="98e62-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="98e62-121">Per eseguire il mapping di una colonna con valori delimitati a un dominio composito</span><span class="sxs-lookup"><span data-stu-id="98e62-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="98e62-122">Fare clic con il pulsante destro del mouse sulla trasformazione DQS Cleansing e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="98e62-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="98e62-123">Nella scheda **Gestione connessione** verificare che il dominio composito sia visualizzato nell'elenco dei domini disponibili.</span><span class="sxs-lookup"><span data-stu-id="98e62-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="98e62-124">Nella scheda **Mapping** selezionare la colonna nell'area **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="98e62-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="98e62-125">Per la colonna elencata nel campo **Colonna di input** selezionare il dominio composito nel campo **Dominio** .</span><span class="sxs-lookup"><span data-stu-id="98e62-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="98e62-126">In base alle esigenze, modificare i nomi visualizzati nei campi **Alias di origine**, **Alias di output**e **Alias di stato** .</span><span class="sxs-lookup"><span data-stu-id="98e62-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="98e62-127">In base alle esigenze, impostare le proprietà nella scheda **Avanzate** . Per altre informazioni sulle proprietà, vedere [Finestra di dialogo Editor trasformazione DQS Cleansing](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="98e62-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e62-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98e62-128">See Also</span></span>  
 [<span data-ttu-id="98e62-129">Trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="98e62-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
