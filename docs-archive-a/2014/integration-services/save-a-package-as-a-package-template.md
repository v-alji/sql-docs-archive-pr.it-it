---
title: Salvare un pacchetto come modello di pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714504"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="7c93b-102">Salvataggio di un pacchetto come modello di pacchetto</span><span class="sxs-lookup"><span data-stu-id="7c93b-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="7c93b-103">In questo argomento viene descritta la procedura per designare e utilizzare pacchetti personalizzati come modelli per la creazione di nuovi pacchetti di Integration Services in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c93b-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7c93b-104">Per impostazione predefinita in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene utilizzato un modello di pacchetto che crea un pacchetto vuoto quando si aggiunge un nuovo pacchetto a un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c93b-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="7c93b-105">Non è possibile sostituire tale modello predefinito, ma è possibile aggiungere nuovi modelli.</span><span class="sxs-lookup"><span data-stu-id="7c93b-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="7c93b-106">È possibile designare più pacchetti da utilizzare come modelli.</span><span class="sxs-lookup"><span data-stu-id="7c93b-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="7c93b-107">Prima di implementare pacchetti personalizzati come modelli è necessario creare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="7c93b-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="7c93b-108">Quando si utilizzano pacchetti personalizzati come modelli per la creazione di nuovi pacchetti, questi ultimi hanno nome e GUID uguali a quelli del modello.</span><span class="sxs-lookup"><span data-stu-id="7c93b-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="7c93b-109">Per distinguere i vari pacchetti è necessario modificare il valore della proprietà `Name` e generare un nuovo GUID per la proprietà `ID`.</span><span class="sxs-lookup"><span data-stu-id="7c93b-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="7c93b-110">Per altre informazioni, vedere [Creare pacchetti in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) e [Impostazione delle proprietà di un pacchetto](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7c93b-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="7c93b-111">Per designare un pacchetto personalizzato come modello di pacchetto</span><span class="sxs-lookup"><span data-stu-id="7c93b-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="7c93b-112">Individuare nel file system il pacchetto che si desidera utilizzare come modello.</span><span class="sxs-lookup"><span data-stu-id="7c93b-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="7c93b-113">Copiare il pacchetto nella cartella DataTransformationItems,</span><span class="sxs-lookup"><span data-stu-id="7c93b-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="7c93b-114">che per impostazione predefinita si trova in C:\Programmi\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="7c93b-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="7c93b-115">Ripetere i passaggi 1 e 2 per ogni pacchetto che si desidera utilizzare come modello.</span><span class="sxs-lookup"><span data-stu-id="7c93b-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="7c93b-116">Per utilizzare un pacchetto personalizzato come modello di pacchetto</span><span class="sxs-lookup"><span data-stu-id="7c93b-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="7c93b-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in cui si desidera creare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7c93b-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="7c93b-118">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi** e quindi **Nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7c93b-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="7c93b-119">Nella finestra di dialogo **Aggiungi nuovo elemento -\<project name>** fare clic sul pacchetto che si vuole usare come modello.</span><span class="sxs-lookup"><span data-stu-id="7c93b-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="7c93b-120">Nell'elenco dei modelli è incluso il modello di pacchetto predefinito Nuovo pacchetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="7c93b-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="7c93b-121">I modelli che è possibile utilizzare come modelli di pacchetto sono identificati dall'icona di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="7c93b-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="7c93b-122">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7c93b-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c93b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c93b-123">See Also</span></span>  
 <span data-ttu-id="7c93b-124">[Creare pacchetti in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7c93b-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="7c93b-125">Pacchetti di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7c93b-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
