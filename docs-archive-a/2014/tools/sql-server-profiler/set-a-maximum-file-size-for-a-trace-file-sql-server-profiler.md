---
title: Impostare le dimensioni massime di un file di traccia (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720616"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="8e346-102">Impostare le dimensioni massime di un file di traccia (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8e346-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="8e346-103">Per impostare le dimensioni massime di un file di traccia, utilizzare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="8e346-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="8e346-104">Per impostare le dimensioni massime di un file di traccia</span><span class="sxs-lookup"><span data-stu-id="8e346-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="8e346-105">Scegliere **Nuova traccia** dal menu **File**e quindi connettersi a un'istanza di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e346-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="8e346-106">Verrà visualizzata la finestra di dialogo **Proprietà traccia**.</span><span class="sxs-lookup"><span data-stu-id="8e346-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e346-107">Se l'opzione **Avvia traccia non appena viene stabilita una connessione**è selezionata, la finestra di dialogo **Proprietà traccia**non viene visualizzata e viene invece avviata la traccia.</span><span class="sxs-lookup"><span data-stu-id="8e346-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="8e346-108">Per disabilitare questa impostazione, scegliere **Opzioni**dal menu **Strumenti**e deselezionare la casella di controllo **Avvia traccia non appena viene stabilita una connessione** .</span><span class="sxs-lookup"><span data-stu-id="8e346-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="8e346-109">Nella casella **Nome traccia** digitare un nome per la traccia.</span><span class="sxs-lookup"><span data-stu-id="8e346-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="8e346-110">Nell'elenco **Nome del modello**selezionare un modello di traccia.</span><span class="sxs-lookup"><span data-stu-id="8e346-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="8e346-111">Selezionare **Salva nel file**e quindi specificare un file per archiviare le informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="8e346-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="8e346-112">Nella casella di controllo **Dimensioni massime del file** specificare le dimensioni massime del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="8e346-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="8e346-113">Quando il file raggiungerà le dimensioni massime specificate, gli eventi di traccia non verranno più registrati in tale file.</span><span class="sxs-lookup"><span data-stu-id="8e346-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="8e346-114">Se si seleziona la casella di controllo **Consenti rollover dei file** , che è selezionata per impostazione predefinita, si verifica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e346-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="8e346-115">Quando il file corrente raggiunge le dimensioni massime, l'opzione di rollover determina la chiusura di tale file in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e la creazione di un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="8e346-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="8e346-116">Le dimensioni del nuovo file corrispondono a quelle del file precedente ma viene aggiunto un numero intero al nome per indicare la relativa sequenza. Se ad esempio il file di traccia originale è denominato filename_1.trc, il nome del file di traccia successivo sarà filename_2.trc, e così via.</span><span class="sxs-lookup"><span data-stu-id="8e346-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="8e346-117">Se il nome assegnato a un nuovo file di rollover è già utilizzato da un file esistente, quest'ultimo verrà sovrascritto a meno che sia di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8e346-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="8e346-118">L'opzione di rollover dei file viene abilitata per impostazione predefinita quando si salvano i dati di traccia in un file.</span><span class="sxs-lookup"><span data-stu-id="8e346-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="8e346-119">Con l'opzione di rollover dei file attivata, la traccia continua fino a quando non viene arrestata in qualche altro modo.</span><span class="sxs-lookup"><span data-stu-id="8e346-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="8e346-120">Per arrestare la traccia dopo che è stato raggiunto il limite delle dimensioni del file, disabilitare l'opzione di rollover.</span><span class="sxs-lookup"><span data-stu-id="8e346-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e346-121">Nel file system FAT32, il limite per le dimensioni dei file è leggermente inferiore a 4 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="8e346-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="8e346-122">Quando il file di traccia raggiunge tali dimensioni, viene visualizzato il messaggio di errore "Spazio su disco insufficiente".</span><span class="sxs-lookup"><span data-stu-id="8e346-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="8e346-123">Per creare file di maggiori dimensioni, utilizzare il file system NTFS.</span><span class="sxs-lookup"><span data-stu-id="8e346-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e346-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e346-124">See Also</span></span>  
 [<span data-ttu-id="8e346-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8e346-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
