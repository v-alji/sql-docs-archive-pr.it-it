---
title: Editor trasformazione Copia colonna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629542"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="3d80b-102">Editor trasformazione Copia colonna</span><span class="sxs-lookup"><span data-stu-id="3d80b-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="3d80b-103">La finestra di dialogo **Editor trasformazione Copia colonna** consente di selezionare le colonne da copiare e di assegnare nomi alle nuove colonne di output.</span><span class="sxs-lookup"><span data-stu-id="3d80b-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="3d80b-104">Per altre informazioni sulla trasformazione Copia colonna, vedere [Trasformazione Copia colonna](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3d80b-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d80b-105">Quando si copiano tutti i dati di origine in una destinazione, potrebbe non essere necessario utilizzare la trasformazione Copia colonna.</span><span class="sxs-lookup"><span data-stu-id="3d80b-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="3d80b-106">In alcuni casi è possibile connettere un'origine direttamente a una destinazione qualora non sia necessaria alcuna trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3d80b-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="3d80b-107">In simili circostanze è spesso preferibile utilizzare l'Importazione/Esportazione guidata SQL Server per creare automaticamente il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3d80b-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="3d80b-108">Successivamente è possibile perfezionare e riconfigurare il pacchetto in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="3d80b-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="3d80b-109">Per altre informazioni, vedere [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3d80b-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d80b-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3d80b-110">Options</span></span>  
 <span data-ttu-id="3d80b-111">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="3d80b-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="3d80b-112">Consente di selezionare le colonne da copiare mediante le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="3d80b-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="3d80b-113">Le selezioni effettuate determinano l'aggiunta delle colonne di input nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="3d80b-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="3d80b-114">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="3d80b-114">**Input Column**</span></span>  
 <span data-ttu-id="3d80b-115">Consente di selezionare le colonne da copiare nell'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="3d80b-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="3d80b-116">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo nella tabella **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="3d80b-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="3d80b-117">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="3d80b-117">**Output Alias**</span></span>  
 <span data-ttu-id="3d80b-118">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="3d80b-118">Type an alias for each new output column.</span></span> <span data-ttu-id="3d80b-119">Per impostazione predefinita viene suggerito **Copia di**seguito dal nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="3d80b-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d80b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d80b-120">See Also</span></span>  
 [<span data-ttu-id="3d80b-121">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="3d80b-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
