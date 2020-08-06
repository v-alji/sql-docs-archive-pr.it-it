---
title: Conversione di schemi XDR con annotazioni in schemi XSD equivalenti (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634938"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="70290-102">Conversione di schemi XDR con annotazioni in schemi XSD equivalenti (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="70290-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="70290-103">Il linguaggio XSD (XML Schema Definition) è il successore del linguaggio XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="70290-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="70290-104">Con l'introduzione del supporto XSD in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, si presuppone che i nuovi schemi con annotazioni vengano creati utilizzando XSD.</span><span class="sxs-lookup"><span data-stu-id="70290-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="70290-105">SQLXML 4.0 include un convertitore da XDR a XSD progettato per consentire la conversione di schemi XDR con annotazioni in schemi XSD equivalenti.</span><span class="sxs-lookup"><span data-stu-id="70290-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70290-106">Dal momento che non si tratta di un convertitore da XDR a XSD universale, è possibile utilizzarlo solo quando si desidera convertire in XSD</span><span class="sxs-lookup"><span data-stu-id="70290-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="70290-107">schemi XDR con annotazioni per l'utilizzo con SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="70290-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="70290-108">Quando vengono utilizzati in altri ambienti, gli schemi XSD convertiti potrebbero non comportarsi come gli schemi XDR originali.</span><span class="sxs-lookup"><span data-stu-id="70290-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="70290-109">Se il file XDR di input specifica la codifica all'interno della dichiarazione XML, questa diventa la codifica del file XSD di output generato.</span><span class="sxs-lookup"><span data-stu-id="70290-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="70290-110">Il convertitore (Cvtschema.exe) viene installato nella cartella Programmi\SQLXML 4.0\bin ed eseguito nel prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="70290-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="70290-111">La sintassi generale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="70290-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="70290-112">Dove:</span><span class="sxs-lookup"><span data-stu-id="70290-112">Where:</span></span>  
  
 <span data-ttu-id="70290-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="70290-113">XDRFileName</span></span>  
 <span data-ttu-id="70290-114">È il nome del file XDR  da convertire in XSD.</span><span class="sxs-lookup"><span data-stu-id="70290-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="70290-115">Lo strumento legge il file XDR di input e crea un file di output XSD nella directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="70290-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="70290-116">Se l'estensione del file di input è .xdr o .xml, il file XSD di output viene creato con lo stesso nome ma con estensione .xsd.</span><span class="sxs-lookup"><span data-stu-id="70290-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="70290-117">Se l'estensione del file di input è diversa da .xml o .xdr (o se manca), il file di output viene creato con lo stesso nome del file di input al quale viene aggiunta l'estensione .xsd.</span><span class="sxs-lookup"><span data-stu-id="70290-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="70290-118">Se ad esempio il nome del file XDR di input è SampleFile.abc, il file XSD risultante viene salvato come SampleFile.abc.xsd.</span><span class="sxs-lookup"><span data-stu-id="70290-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="70290-119">-y</span><span class="sxs-lookup"><span data-stu-id="70290-119">-y</span></span>  
 <span data-ttu-id="70290-120">(Facoltativo) Sovrascrive il file XSD esistente con il file XSD generato dal convertitore.</span><span class="sxs-lookup"><span data-stu-id="70290-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="70290-121">Se non viene specificato il flag, il convertitore richiede di specificare se si desidera sovrascrivere il file XSD esistente e offre l'opportunità di modificare il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="70290-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="70290-122">-w</span><span class="sxs-lookup"><span data-stu-id="70290-122">-w</span></span>  
 <span data-ttu-id="70290-123">(Facoltativo) Restituisce avvisi non irreversibili generati nel processo di conversione dallo strumento.</span><span class="sxs-lookup"><span data-stu-id="70290-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="70290-124">Per impostazione predefinita, lo strumento visualizza messaggi solo per gli errori irreversibili.</span><span class="sxs-lookup"><span data-stu-id="70290-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="70290-125">-?</span><span class="sxs-lookup"><span data-stu-id="70290-125">-?</span></span>  
 <span data-ttu-id="70290-126">Restituisce un elenco di opzioni che è possibile specificare con `cvtschema`, insieme a una spiegazione.</span><span class="sxs-lookup"><span data-stu-id="70290-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70290-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70290-127">See Also</span></span>  
 <span data-ttu-id="70290-128">[Mapping dei tipi di dati XSD ai tipi di dati XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="70290-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="70290-129">Annotazioni XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="70290-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
