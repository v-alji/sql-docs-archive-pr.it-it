---
title: Oggetti di automazione OLE in Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638376"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="ae5d6-102">Oggetti di automazione OLE in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae5d6-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ae5d6-103">include varie stored procedure di sistema che consentono di fare riferimento agli oggetti di automazione OLE in batch, stored procedure e trigger [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae5d6-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="ae5d6-104">Queste stored procedure di sistema vengono eseguite come stored procedure estese e gli oggetti di automazione OLE eseguiti tramite tali stored procedure vengono eseguiti nello spazio degli indirizzi di un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] esattamente come le stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="ae5d6-105">Le stored procedure di automazione OLE consentono di fare riferimento in batch [!INCLUDE[tsql](../../includes/tsql-md.md)] a oggetti SQL-DMO e a oggetti di automazione OLE personalizzati, ad esempio gli oggetti che espongono l'interfaccia **IDispatch** .</span><span class="sxs-lookup"><span data-stu-id="ae5d6-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="ae5d6-106">Un server OLE in-process personalizzato creato in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] deve includere un gestore degli errori, specificato con l'istruzione **On Error GoTo**, per le subroutine **Class_Initialize** e **Class_Terminate**.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="ae5d6-107">Gli errori non gestiti nelle subroutine **Class_Initialize** e **Class_Terminate** possono provocare errori imprevedibili, ad esempio una violazione dell'accesso in un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae5d6-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="ae5d6-108">È consigliabile disporre inoltre dei gestori degli errori per altre subroutine.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="ae5d6-109">Per usare un oggetto di automazione OLE in [!INCLUDE[tsql](../../includes/tsql-md.md)] , prima di tutto è necessario chiamare la stored procedure di sistema **sp_OACreate** per creare un'istanza dell'oggetto nello spazio degli indirizzi del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae5d6-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="ae5d6-110">Richiamare quindi le stored procedure seguenti per utilizzare le proprietà, i metodi e le informazioni sugli errori dell'oggetto:</span><span class="sxs-lookup"><span data-stu-id="ae5d6-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="ae5d6-111">**sp_OAGetProperty** recupera il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="ae5d6-112">**sp_OASetProperty** imposta il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="ae5d6-113">**sp_OAMethod** chiama un metodo.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="ae5d6-114">**sp_OAGetErrorInfo** recupera informazioni sugli errori più recenti.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="ae5d6-115">Quando l'oggetto non è più necessario, chiamare **sp_OADestroy** per deallocare l'istanza dell'oggetto creata con **sp_OACreate**.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="ae5d6-116">Gli oggetti di automazione OLE restituiscono dati tramite valori e metodi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="ae5d6-117">**sp_OAGetProperty** e **sp_OAMethod** restituiscono questi valori dei dati sotto forma di set di risultati.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="ae5d6-118">L'ambito di un oggetto di automazione OLE è il batch.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="ae5d6-119">Tutti i riferimenti all'oggetto devono essere inclusi in un unico batch, stored procedure o trigger.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="ae5d6-120">Gli oggetti di automazione OLE di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supportano l'attraversamento dell'oggetto a cui fanno riferimento per accedere agli altri oggetti che contiene.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="ae5d6-121">Se, ad esempio, si usa l'oggetto SQL-DMO di **SQLServer** , è possibile fare riferimento ai database e alle tabelle disponibili in tale server.</span><span class="sxs-lookup"><span data-stu-id="ae5d6-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ae5d6-122">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="ae5d6-122">Related Content</span></span>  
 [<span data-ttu-id="ae5d6-123">Sintassi della gerarchia degli oggetti &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="ae5d6-124">Configurazione superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="ae5d6-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="ae5d6-125">Opzione di configurazione del server Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="ae5d6-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="ae5d6-126">sp_OACreate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="ae5d6-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="ae5d6-128">sp_OASetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="ae5d6-129">sp_OAMethod &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="ae5d6-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="ae5d6-131">sp_OADestroy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae5d6-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
