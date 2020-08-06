---
title: Documenti e script per un database Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML for Analysis, scripts
- XMLA, scripts
- scripts [Analysis Services], databases
- documenting databases
- databases [Analysis Services], documenting
- databases [Analysis Services], scripts
ms.assetid: 125044e2-8d36-4733-8743-8bb68ff9aa4e
author: minewiskan
ms.author: owend
ms.openlocfilehash: cfe008b0d6903d7d012eb57d41d6e50240202ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636904"
---
# <a name="document-and-script-an-analysis-services-database"></a><span data-ttu-id="39dad-102">Documentazione e script per un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="39dad-102">Document and Script an Analysis Services Database</span></span>
  <span data-ttu-id="39dad-103">Dopo la distribuzione di un database [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , è possibile usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per generare l'output dei metadati del database o di un oggetto contenuto nel database in formato di script XMLA (XML for Analysis).</span><span class="sxs-lookup"><span data-stu-id="39dad-103">After an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script.</span></span> <span data-ttu-id="39dad-104">È possibile salvare l'output di questo script in una nuova finestra dell' **Editor di query XMLA** , in un file o negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="39dad-104">You can output this script to a new **XMLA Query Editor** window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="39dad-105">Per ulteriori informazioni su XMLA, vedere [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="39dad-105">For more information about XMLA, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
 <span data-ttu-id="39dad-106">Lo script XMLA generato utilizza gli elementi ASSL ( [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language) per definire gli oggetti contenuti nello script.</span><span class="sxs-lookup"><span data-stu-id="39dad-106">The generated XMLA script uses [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) elements to define the objects contained by the script.</span></span> <span data-ttu-id="39dad-107">Se è stato generato uno script CREATE, lo script XMLA risultante contiene un comando XMLA **Create** e gli elementi ASSL che consentono di creare l'intera struttura del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in un'istanza.</span><span class="sxs-lookup"><span data-stu-id="39dad-107">If you generated a CREATE script, the resulting XMLA script contains an XMLA **Create** command and ASSL elements that can be used to create the entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database structure on an instance.</span></span> <span data-ttu-id="39dad-108">Se è stato generato uno script ALTER, lo script XMLA risultante contiene un comando XMLA **Alter** e gli elementi ASSL che consentono di ripristinare lo stato in cui si trovava la struttura di un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esistente al momento della creazione dello script.</span><span class="sxs-lookup"><span data-stu-id="39dad-108">If you generated an ALTER script, the resulting XMLA script contains an XMLA **Alter** command and ASSL elements that can be used to restore the structure of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database to the state of the database at the time the script was created.</span></span>  
  
 <span data-ttu-id="39dad-109">È possibile utilizzare in vari modi lo script XMLA generato da un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , ad esempio per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="39dad-109">You can use the generated XMLA script from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in many ways, including:</span></span>  
  
-   <span data-ttu-id="39dad-110">Per mantenere uno script di backup che consente di ricreare tutti gli oggetti e le autorizzazioni di database.</span><span class="sxs-lookup"><span data-stu-id="39dad-110">To maintain a backup script that allows you to recreate all the database objects and permissions.</span></span>  
  
-   <span data-ttu-id="39dad-111">Per creare o aggiornare il codice di sviluppo del database.</span><span class="sxs-lookup"><span data-stu-id="39dad-111">To create or update database development code.</span></span>  
  
-   <span data-ttu-id="39dad-112">Per creare un ambiente di prova o di sviluppo da uno schema esistente.</span><span class="sxs-lookup"><span data-stu-id="39dad-112">To create a test or development environment from an existing schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39dad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39dad-113">See Also</span></span>  
 <span data-ttu-id="39dad-114">[Modificare o eliminare un database di Analysis Services](modify-or-delete-an-analysis-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="39dad-114">[Modify or Delete an Analysis Services Database](modify-or-delete-an-analysis-services-database.md) </span></span>  
 <span data-ttu-id="39dad-115">[Alter element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="39dad-115">[Alter Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span></span>  
 [<span data-ttu-id="39dad-116">Elemento Create &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="39dad-116">Create Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)  
  
  
