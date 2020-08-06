---
title: Formati di dati per l'importazione o l'esportazione bulk (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623265"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="e1772-102">Formati di dati per l'importazione o l'esportazione bulk (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1772-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e1772-103">può accettare dati nel formato dati di tipo carattere o nel formato dati binario nativo.</span><span class="sxs-lookup"><span data-stu-id="e1772-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="e1772-104">Utilizzare il formato carattere se vengono spostati dati tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e un'altra applicazione (ad esempio [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) o un altro server di database (ad esempio Oracle o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e1772-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="e1772-105">È possibile utilizzare il formato nativo unicamente se si trasferiscono dati tra due istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1772-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e1772-106">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="e1772-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="e1772-107">Formati di dati per l'importazione o l'esportazione bulk</span><span class="sxs-lookup"><span data-stu-id="e1772-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="e1772-108">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e1772-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="e1772-109">Formati di dati per l'importazione o l'esportazione bulk</span><span class="sxs-lookup"><span data-stu-id="e1772-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="e1772-110">Nella tabella seguente viene indicato quale formato di dati è generalmente appropriato utilizzare in base alla modalità di rappresentazione dei dati e all'origine o destinazione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e1772-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="e1772-111">Operazione</span><span class="sxs-lookup"><span data-stu-id="e1772-111">Operation</span></span>|<span data-ttu-id="e1772-112">Nativo</span><span class="sxs-lookup"><span data-stu-id="e1772-112">Native</span></span>|<span data-ttu-id="e1772-113">nativi Unicode</span><span class="sxs-lookup"><span data-stu-id="e1772-113">Unicode native</span></span>|<span data-ttu-id="e1772-114">Carattere</span><span class="sxs-lookup"><span data-stu-id="e1772-114">Character</span></span>|<span data-ttu-id="e1772-115">carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="e1772-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="e1772-116">Trasferimenti bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite un file di dati che non contiene caratteri estesi o DBCS (Double-Byte Character Set).</span><span class="sxs-lookup"><span data-stu-id="e1772-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="e1772-117">A meno che non venga utilizzato un file di formato, la definizione delle tabelle deve essere identica.</span><span class="sxs-lookup"><span data-stu-id="e1772-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="e1772-118">Sì<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e1772-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="e1772-119">Per le colonne `sql_variant` è consigliabile utilizzare il formato di dati nativo perché, a differenza dei formati carattere o Unicode, mantiene i metadati per ogni valore `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="e1772-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="e1772-120">Sì</span><span class="sxs-lookup"><span data-stu-id="e1772-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="e1772-121">Trasferimenti bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite un file di dati contenente caratteri estesi o DBCS.</span><span class="sxs-lookup"><span data-stu-id="e1772-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="e1772-122">Sì</span><span class="sxs-lookup"><span data-stu-id="e1772-122">Yes</span></span>|-|-|  
|<span data-ttu-id="e1772-123">Importazione bulk di dati da un file di testo creato da un altro programma.</span><span class="sxs-lookup"><span data-stu-id="e1772-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="e1772-124">Sì</span><span class="sxs-lookup"><span data-stu-id="e1772-124">Yes</span></span>|-|  
|<span data-ttu-id="e1772-125">Esportazione bulk di dati in un file di testo che verrà utilizzato in un altro programma.</span><span class="sxs-lookup"><span data-stu-id="e1772-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="e1772-126">Sì</span><span class="sxs-lookup"><span data-stu-id="e1772-126">Yes</span></span>|-|  
|<span data-ttu-id="e1772-127">Trasferimenti bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite un file di dati contenente dati Unicode e che non contiene caratteri estesi o DBCS.</span><span class="sxs-lookup"><span data-stu-id="e1772-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="e1772-128">Sì</span><span class="sxs-lookup"><span data-stu-id="e1772-128">Yes</span></span>|  
  
 <span data-ttu-id="e1772-129"><sup>1</sup> metodo più veloce per l'esportazione bulk di dati da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando si usa **bcp**.</span><span class="sxs-lookup"><span data-stu-id="e1772-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e1772-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e1772-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e1772-131">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1772-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e1772-132">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1772-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e1772-133">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1772-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e1772-134">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1772-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e1772-135">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1772-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1772-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1772-136">See Also</span></span>  
 <span data-ttu-id="e1772-137">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e1772-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="e1772-138">Specificare i formati di dati per la compatibilità con bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1772-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
