---
title: Editor gestione connessione Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629507"
---
# <a name="excel-connection-manager-editor"></a><span data-ttu-id="b1664-102">Editor gestione connessione Excel</span><span class="sxs-lookup"><span data-stu-id="b1664-102">Excel Connection Manager Editor</span></span>
  <span data-ttu-id="b1664-103">Usare la finestra di dialogo \*\*Editor gestione connessione Excel[!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]per aggiungere una connessione a un file di cartella di lavoro di \*\* nuovo o esistente.</span><span class="sxs-lookup"><span data-stu-id="b1664-103">Use the **Excel Connection Manager Editor** dialog box to add a connection to an existing or a new [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook file.</span></span>  
  
 <span data-ttu-id="b1664-104">Per altre informazioni sulla gestione connessioni Excel, vedere [Gestione connessione Excel](connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b1664-104">To learn more about the Excel connection manager, see [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1664-105">Non è possibile connettersi a un file di Excel protetto da password.</span><span class="sxs-lookup"><span data-stu-id="b1664-105">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b1664-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b1664-106">Options</span></span>  
 <span data-ttu-id="b1664-107">**Percorso file di Excel**</span><span class="sxs-lookup"><span data-stu-id="b1664-107">**Excel file path**</span></span>  
 <span data-ttu-id="b1664-108">Consente di digitare il percorso e il nome del file di una cartella di lavoro di Excel (xls) nuova o esistente.</span><span class="sxs-lookup"><span data-stu-id="b1664-108">Type the path and file name of an existing or a new Excel workbook file (.xls).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="b1664-109">**Editor destinazione Excel** crea automaticamente il file di Excel quando si seleziona una **connessione Excel** che fa riferimento a un file nuovo o non esistente e quindi si fa clic su **nuovo** per **nome del foglio di Excel**.</span><span class="sxs-lookup"><span data-stu-id="b1664-109">The **Excel Destination Editor** automatically creates the Excel file when you select an **Excel Connection** that points to a new/non-existent file and then click **New** for **Name of the Excel Sheet**.</span></span>  
  
 <span data-ttu-id="b1664-110">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="b1664-110">**Browse**</span></span>  
 <span data-ttu-id="b1664-111">Utilizzare la finestra di dialogo **Apri** per passare alla cartella in cui è presente il file di Excel o in cui si desidera creare il nuovo file.</span><span class="sxs-lookup"><span data-stu-id="b1664-111">Use the **Open** dialog box to navigate to the folder in which the excel file exists or where you want to create the new file.</span></span>  
  
 <span data-ttu-id="b1664-112">**Versione di Excel**</span><span class="sxs-lookup"><span data-stu-id="b1664-112">**Excel version**</span></span>  
 <span data-ttu-id="b1664-113">Consente di specificare la versione di Microsoft Excel utilizzata per creare il file.</span><span class="sxs-lookup"><span data-stu-id="b1664-113">Specify the version of Microsoft Excel that was used to create the file.</span></span>  
  
|<span data-ttu-id="b1664-114">Opzione</span><span class="sxs-lookup"><span data-stu-id="b1664-114">Option</span></span>|<span data-ttu-id="b1664-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1664-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b1664-116">Microsoft Excel 97-2005</span><span class="sxs-lookup"><span data-stu-id="b1664-116">Excel 97-2003</span></span>|<span data-ttu-id="b1664-117">Il file è stato creato utilizzando Microsoft Excel 97 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b1664-117">File was created using Excel 97 or later.</span></span>|  
|<span data-ttu-id="b1664-118">Excel 3,0</span><span class="sxs-lookup"><span data-stu-id="b1664-118">Excel 3.0</span></span>|<span data-ttu-id="b1664-119">Il file è stato creato con Excel 3,0.</span><span class="sxs-lookup"><span data-stu-id="b1664-119">File was created using Excel 3.0.</span></span>|  
|<span data-ttu-id="b1664-120">Excel 4,0</span><span class="sxs-lookup"><span data-stu-id="b1664-120">Excel 4.0</span></span>|<span data-ttu-id="b1664-121">Il file è stato creato utilizzando Microsoft Excel 4.0.</span><span class="sxs-lookup"><span data-stu-id="b1664-121">File was created using Excel 4.0.</span></span>|  
|<span data-ttu-id="b1664-122">Excel 5,0</span><span class="sxs-lookup"><span data-stu-id="b1664-122">Excel 5.0</span></span>|<span data-ttu-id="b1664-123">Il file è stato creato utilizzando Microsoft Excel 95 (versione 7.0).</span><span class="sxs-lookup"><span data-stu-id="b1664-123">File was created using Excel 95 (7.0).</span></span>|  
  
 <span data-ttu-id="b1664-124">**La prima riga contiene nomi di colonna**</span><span class="sxs-lookup"><span data-stu-id="b1664-124">**First row has column names**</span></span>  
 <span data-ttu-id="b1664-125">Consente di specificare se la prima riga di dati del foglio di lavoro selezionato contiene nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="b1664-125">Specify whether the first row of data in the selected worksheet contains column names.</span></span> <span data-ttu-id="b1664-126">Il valore predefinito di questa opzione è **True**.</span><span class="sxs-lookup"><span data-stu-id="b1664-126">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1664-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1664-127">See Also</span></span>  
 <span data-ttu-id="b1664-128">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b1664-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="b1664-129">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="b1664-129">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
