---
title: Formato del pacchetto SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715560"
---
# <a name="ssis-package-format"></a><span data-ttu-id="d1ebd-102">Formato del pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="d1ebd-102">SSIS Package Format</span></span>
  <span data-ttu-id="d1ebd-103">Nella versione corrente di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]sono state apportate modifiche significative al formato dei pacchetti (file DTSX) per semplificare la lettura del formato e il confronto dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="d1ebd-104">È anche possibile unire in modo più affidabile pacchetti che non contengono modifiche in conflitto o modifiche archiviate in formato binario.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="d1ebd-105">Per visualizzare il formato di file del pacchetto DTSX corrente, vedere [ \[ MS-DTSX \] : specifica del formato di file XML del pacchetto Data Transformation Services](https://go.microsoft.com/fwlink/?LinkId=233251).</span><span class="sxs-lookup"><span data-stu-id="d1ebd-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="d1ebd-106">Nell'elenco seguente vengono indicate le modifiche al formato del file.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="d1ebd-107">Per visualizzare gli esempi di codice di queste modifiche, vedere la pagina relativa alle [modifiche al formato del pacchetto in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span><span class="sxs-lookup"><span data-stu-id="d1ebd-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="d1ebd-108">Sono state applicate convenzioni di formattazione per semplificare la lettura e la comprensione del file DTSX.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="d1ebd-109">Il formato è più conciso.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-109">The format is more concise.</span></span> <span data-ttu-id="d1ebd-110">Gli elementi separati per ogni proprietà sono stati resi persistenti come gli attributi, ad eccezione di PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="d1ebd-111">Gli attributi sono elencati in ordine alfabetico e le proprietà con valori predefiniti non sono più persistenti.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="d1ebd-112">Infine, gli elementi che possono essere visualizzati più volte, sono ora contenuti all'interno di un elemento padre.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="d1ebd-113">La maggior parte degli oggetti all'interno di un pacchetto che può fare riferimento ad altri oggetti contiene ora un attributo `refId` definito nel pacchetto XML.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="d1ebd-114">Anziché rendere persistente gli ID di derivazione, ora è stato reso persistente `refID`.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="d1ebd-115">Gli ID di derivazione vengono ancora utilizzati all'interno del runtime e vengono rigenerati al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="d1ebd-116">Il valore `refId` è una stringa univoca leggibile e comprensibile, rispetto ai valori GUID o ai valori integer.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="d1ebd-117">La stringa è simile ai valori del percorso utilizzati per le configurazioni del pacchetto nelle versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1ebd-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="d1ebd-118">Se si uniscono le modifiche tra due versioni di un pacchetto, `refId` può essere utilizzato nelle operazioni di ricerca e sostituzione per verificare che tutti i riferimenti all'oggetto siano stati aggiornati correttamente.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="d1ebd-119">Le informazioni sul layout sono contenute in una sezione CData.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="d1ebd-120">Le annotazioni sono persistenti in testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="d1ebd-121">In questo modo è più facile estrarre le informazioni per la generazione automatica della documentazione.</span><span class="sxs-lookup"><span data-stu-id="d1ebd-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
