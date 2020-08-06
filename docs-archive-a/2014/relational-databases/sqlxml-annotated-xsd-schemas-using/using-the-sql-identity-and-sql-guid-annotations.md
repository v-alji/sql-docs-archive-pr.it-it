---
title: 'Uso delle annotazioni SQL: Identity e SQL: GUID | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:guid
- annotated XSD schemas, IDENTITY-type columns
- annotated XSD schemas, GUID values
- DiffGrams [SQLXML], annotations
- identity annotation
- XSD schemas [SQLXML], GUID values
- GUIDs [SQLXML]
- guid annotation
- sql:identity
- IDENTITY-type column
- XSD schemas [SQLXML], IDENTITY-type columns
- updategrams [SQLXML], GUID values
ms.assetid: 7661dfd0-6573-4692-a8f1-3597adcd33c4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc5c08f158911edb0a1a0638fc4bcee1e05a248c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628610"
---
# <a name="using-the-sqlidentity-and-sqlguid-annotations"></a><span data-ttu-id="f19e0-102">Utilizzo delle annotazioni sql:identity e sql:guid</span><span class="sxs-lookup"><span data-stu-id="f19e0-102">Using the sql:identity and sql:guid Annotations</span></span>
  <span data-ttu-id="f19e0-103">È possibile specificare le `sql:identity` `sql:guid` annotazioni e in uno schema XSD su qualsiasi nodo che esegue il mapping a una colonna del database in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f19e0-103">You can specify the `sql:identity` and `sql:guid` annotations in an XSD schema on any node that maps to a database column in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f19e0-104">Il formato dell'updategram supporta gli attributi `updg:at-identity` e `updg:guid` che invece non vengono supportati dal formato DiffGram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-104">Whereas the updategram format supports the `updg:at-identity` and `updg:guid` attributes, the DiffGram format does not.</span></span> <span data-ttu-id="f19e0-105">L'attributo `updg:at-identity` definisce il comportamento relativo all'aggiornamento di una colonna di tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="f19e0-105">The `updg:at-identity` attribute defines the behavior in updating an IDENTITY-type column.</span></span> <span data-ttu-id="f19e0-106">L'attributo `updg:guid` consente di ottenere un valore GUID da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e di utilizzarlo nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-106">The `updg:guid` attribute allows you to obtain a GUID value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and use it in the updategram.</span></span> <span data-ttu-id="f19e0-107">Per ulteriori informazioni ed esempi reali, vedere [inserimento di dati mediante UPDATEGRAM XML &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f19e0-107">For more information and working samples, see [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="f19e0-108">Le annotazioni `sql:identity` e `sql:guid` estendono questa funzionalità ai DiffGram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-108">The `sql:identity` and `sql:guid` annotations extend this functionality to DiffGrams.</span></span>  
  
 <span data-ttu-id="f19e0-109">Per eseguire un DiffGram, è necessario prima convertirlo in updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-109">When you execute a DiffGram, it is first converted to an updategram, and then the updategram is executed.</span></span> <span data-ttu-id="f19e0-110">Specificando le annotazioni `sql:identity` e `sql:guid` nello schema XSD, di fatto si definisce il comportamento di un updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-110">By specifying the `sql:identity` and `sql:guid` annotations in the XSD schema, you are in fact defining the behavior of an updategram.</span></span> <span data-ttu-id="f19e0-111">Tutte le annotazioni vengono pertanto descritte nel contesto di un updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-111">Therefore, all the annotations are described in the context of an updategram.</span></span> <span data-ttu-id="f19e0-112">Le annotazioni possono essere utilizzate sia per i DiffGram che per gli updategram. Per gli updategram è tuttavia già disponibile una modalità di gestione dell'identità e dei valori GUID più potente.</span><span class="sxs-lookup"><span data-stu-id="f19e0-112">The annotations can be used both for DiffGrams and updategrams; however, updategrams already provide a more powerful way of handling identity and GUID values.</span></span>  
  
 <span data-ttu-id="f19e0-113">Le annotazioni `sql:identity` e `sql:guid` possono essere definite su un elemento di contenuto complesso.</span><span class="sxs-lookup"><span data-stu-id="f19e0-113">The `sql:identity` and `sql:guid` annotations can be defined on a complex content element.</span></span>  
  
## <a name="sqlidentity-annotation"></a><span data-ttu-id="f19e0-114">Annotazione sql:identity</span><span class="sxs-lookup"><span data-stu-id="f19e0-114">sql:identity Annotation</span></span>  
 <span data-ttu-id="f19e0-115">È possibile specificare l'annotazione `sql:identity` nello schema XSD su qualsiasi nodo che esegue il mapping a una colonna di database di tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="f19e0-115">You can specify the `sql:identity` annotation in the XSD schema on any node that maps to an IDENTITY-type database column.</span></span> <span data-ttu-id="f19e0-116">Il valore specificato per questa annotazione definisce il modo in cui viene aggiornata la colonna di tipo IDENTITY, usando il valore fornito nell'updategram per modificare la colonna o ignorando il valore, nel qual caso [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene usato un valore generato da per questa colonna.</span><span class="sxs-lookup"><span data-stu-id="f19e0-116">The value specified for this annotation defines how the IDENTITY-type column is updated (either by using the value provided in the updategram to modify the column or by ignoring the value, in which case a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-generated value is used for this column).</span></span>  
  
 <span data-ttu-id="f19e0-117">All'annotazione `sql:identity` è possibile assegnare due valori:</span><span class="sxs-lookup"><span data-stu-id="f19e0-117">The `sql:identity` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="f19e0-118">ignore</span><span class="sxs-lookup"><span data-stu-id="f19e0-118">ignore</span></span>  
 <span data-ttu-id="f19e0-119">Indica all'updategram di ignorare qualsiasi valore fornito nell'updategram per la colonna in oggetto e di generare il valore Identity in base a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f19e0-119">Directs the updategram to ignore any value that is provided in the updategram for that column and to rely on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate the identity value.</span></span>  
  
 <span data-ttu-id="f19e0-120">useValue</span><span class="sxs-lookup"><span data-stu-id="f19e0-120">useValue</span></span>  
 <span data-ttu-id="f19e0-121">Indica all'updategram di utilizzare il valore fornito nell'updategram per aggiornare la colonna di tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="f19e0-121">Directs the updategram to use the value that is provided in the updategram to update the IDENTITY-type column.</span></span> <span data-ttu-id="f19e0-122">Un updategram non controlla se la colonna è un valore Identity.</span><span class="sxs-lookup"><span data-stu-id="f19e0-122">An updategram does not check whether the column is an identity value or not.</span></span>  
  
 <span data-ttu-id="f19e0-123">Se l'updategram specifica un valore per la colonna di tipo IDENTITY, è necessario specificare `sql:identity="useValue"` nello schema.</span><span class="sxs-lookup"><span data-stu-id="f19e0-123">If the updategram specifies a value for the IDENTITY-type column, the `sql:identity="useValue"` must be specified in the schema.</span></span>  
  
## <a name="sqlguid-annotation"></a><span data-ttu-id="f19e0-124">Annotazione sql:guid</span><span class="sxs-lookup"><span data-stu-id="f19e0-124">sql:guid Annotation</span></span>  
 <span data-ttu-id="f19e0-125">Un valore GUID può essere generato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quindi utilizzato nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-125">An updategram can have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generate a GUID value and then use this value in the updategram.</span></span> <span data-ttu-id="f19e0-126">Nel contesto dei DiffGram è possibile utilizzare l'annotazione `sql:guid` per specificare se utilizzare un valore GUID generato da SQL Server oppure il valore fornito nell'updategram per la colonna specifica.</span><span class="sxs-lookup"><span data-stu-id="f19e0-126">In the context of DiffGrams, you can use the `sql:guid` annotation to specify whether to use a GUID value that is generated by SQL Server or use the value that is provided in the updategram for that column.</span></span>  
  
 <span data-ttu-id="f19e0-127">All'annotazione `sql:guid` è possibile assegnare due valori:</span><span class="sxs-lookup"><span data-stu-id="f19e0-127">The `sql:guid` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="f19e0-128">generate</span><span class="sxs-lookup"><span data-stu-id="f19e0-128">generate</span></span>  
 <span data-ttu-id="f19e0-129">Specifica che il valore GUID generato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere utilizzato per la colonna specifica nell'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f19e0-129">Specifies that the GUID generated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] be used for that column in the update operation.</span></span>  
  
 <span data-ttu-id="f19e0-130">useValue</span><span class="sxs-lookup"><span data-stu-id="f19e0-130">useValue</span></span>  
 <span data-ttu-id="f19e0-131">Specifica che per la colonna deve essere utilizzato il valore specificato nell'updategram.</span><span class="sxs-lookup"><span data-stu-id="f19e0-131">Specifies that the value specified in the updategram be used for the column.</span></span> <span data-ttu-id="f19e0-132">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f19e0-132">This is the default value.</span></span>  
  
  
