---
title: Trasformazione Cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629952"
---
# <a name="cache-transform"></a><span data-ttu-id="6b636-102">trasformazione Cache</span><span class="sxs-lookup"><span data-stu-id="6b636-102">Cache Transform</span></span>
  <span data-ttu-id="6b636-103">La trasformazione Cache genera un set di dati di riferimento per la trasformazione Ricerca mediante la scrittura di dati da un'origine dati connessa nel flusso di dati a una gestione connessione cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="6b636-104">La trasformazione Ricerca esegue ricerche unendo in join i dati contenuti nelle colonne di input da un'origine dati connessa con le colonne nel database di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6b636-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="6b636-105">È possibile utilizzare la gestione connessione Cache quando si desidera configurare la trasformazione Ricerca per l'esecuzione in modalità Full Cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="6b636-106">In questa modalità, il set di dati di riferimento viene caricato nella cache prima dell'esecuzione della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="6b636-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="6b636-107">Per istruzioni su come configurare la trasformazione Ricerca in modalità Full Cache utilizzando la gestione connessione cache e una trasformazione Cache, vedere [Implementazione di una trasformazione Ricerca in modalità Full Cache utilizzando la gestione connessione della cache](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6b636-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6b636-108">Per ulteriori informazioni sulla memorizzazione nella cache del set di dati di riferimento, vedere [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6b636-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b636-109">La Trasformazione cache scrive solo righe univoche nella gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="6b636-110">In un pacchetto singolo, solo una trasformazione Cache può scrivere i dati nella stessa gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="6b636-111">Se il pacchetto contiene più trasformazioni Cache, la prima ad essere chiamata quando il pacchetto viene eseguito è quella che scrive i dati nella gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="6b636-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="6b636-112">Le operazioni di scrittura delle trasformazioni Cache successive non vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="6b636-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="6b636-113">Per ulteriori informazioni, vedere [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) e [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6b636-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="6b636-114">Configurazione della trasformazione Cache</span><span class="sxs-lookup"><span data-stu-id="6b636-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="6b636-115">È possibile configurare la gestione connessione della cache in modo da salvare i dati in un file di cache (con estensione caw).</span><span class="sxs-lookup"><span data-stu-id="6b636-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="6b636-116">Per configurare la trasformazione Cache, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6b636-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="6b636-117">Specificare la gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="6b636-118">Eseguire il mapping delle colonne di input nella trasformazione Cache alle colonne di destinazione nella gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="6b636-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b636-119">È necessario eseguire il mapping di ogni colonna di input a una colonna di destinazione e i tipi di dati di colonna devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="6b636-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="6b636-120">In caso contrario, in Progettazione [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="6b636-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="6b636-121">È possibile utilizzare **Editor gestione connessione della cache** per modificare i tipi di dati, i nomi e altre proprietà delle colonne.</span><span class="sxs-lookup"><span data-stu-id="6b636-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="6b636-122">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b636-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="6b636-123">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** , vedere [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6b636-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="6b636-124">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6b636-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b636-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b636-125">See Also</span></span>  
 <span data-ttu-id="6b636-126">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="6b636-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="6b636-127">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="6b636-127">Data Flow</span></span>](../data-flow.md)  
  
  
