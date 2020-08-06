---
title: Copiare un pacchetto in SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629543"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="dcc3f-102">Copiare un pacchetto in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="dcc3f-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="dcc3f-103">In questo argomento viene descritto come creare un nuovo pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tramite la copia di un pacchetto esistente e come aggiornare le proprietà `Name` e `GUID` del nuovo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="dcc3f-104">Per copiare un pacchetto</span><span class="sxs-lookup"><span data-stu-id="dcc3f-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="dcc3f-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="dcc3f-106">In Esplora soluzioni fare doppio clic sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="dcc3f-107">Verificare che il pacchetto da copiare sia selezionato in Esplora soluzioni o che la scheda attiva in Progettazione SSIS sia quella che contiene il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="dcc3f-108">Scegliere **Apri** dal menu **Salva \<package name> File**.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcc3f-109">Il comando **Salva con nome** è disponibile nel menu **File** solo se il pacchetto è aperto in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="dcc3f-110">Facoltativamente, passare a un'altra cartella.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="dcc3f-111">Modificare il nome del file del pacchetto,</span><span class="sxs-lookup"><span data-stu-id="dcc3f-111">Update the name of the package file.</span></span> <span data-ttu-id="dcc3f-112">ricordando di mantenere l'estensione dtsx.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="dcc3f-113">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="dcc3f-114">Quando richiesto specificare se aggiornare il nome dell'oggetto di pacchetto in modo che corrisponda al nome del file.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="dcc3f-115">Se si fa clic su **Sì**, la `Name` proprietà del pacchetto verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="dcc3f-116">Il nuovo pacchetto viene aggiunto al progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e aperto in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcc3f-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="dcc3f-117">Facoltativamente, fare clic sullo sfondo della scheda **Flusso di controllo** e quindi su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="dcc3f-118">Nella finestra Proprietà fare clic sul valore della proprietà ID, quindi selezionare nell'elenco a discesa **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="dcc3f-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="dcc3f-119">Scegliere **Salva elementi selezionati** dal menu **File** per salvare il nuovo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="dcc3f-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc3f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcc3f-120">See Also</span></span>  
 <span data-ttu-id="dcc3f-121">[Salvataggio di una copia di un pacchetto](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="dcc3f-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="dcc3f-122">[Creare pacchetti in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="dcc3f-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="dcc3f-123">Pacchetti di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="dcc3f-123">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
