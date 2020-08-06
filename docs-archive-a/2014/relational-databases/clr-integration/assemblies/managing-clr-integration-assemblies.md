---
title: Gestione degli assembly di integrazione CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720022"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="0ec58-102">Gestione degli assembly dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="0ec58-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="0ec58-103">Il codice gestito viene compilato e quindi distribuito in unità denominate assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec58-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="0ec58-104">Un assembly viene compresso come DLL o file eseguibile (con estensione exe).</span><span class="sxs-lookup"><span data-stu-id="0ec58-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="0ec58-105">Mentre un file eseguibile può essere eseguito in modo autonomo, una DLL deve essere ospitata in un'applicazione esistente.</span><span class="sxs-lookup"><span data-stu-id="0ec58-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="0ec58-106">Gli assembly DLL gestiti possono essere caricati e ospitati da [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ec58-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="0ec58-107">database che utilizza l'istruzione CREATE ASSEMBLY, prima che possa essere caricato nel processo e utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0ec58-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="0ec58-108">Gli assembly possono inoltre essere aggiornati a una versione più recente tramite l'istruzione ALTER ASSEMBLY o rimossi da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'istruzione DROP ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="0ec58-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="0ec58-109">Le informazioni sugli assembly vengono archiviate nella tabella `sys.assembly_files` del database in cui è stato installato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec58-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="0ec58-110">La tabella `sys.assembly_files` contiene le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="0ec58-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="0ec58-111">Colonna</span><span class="sxs-lookup"><span data-stu-id="0ec58-111">Column</span></span>|<span data-ttu-id="0ec58-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ec58-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0ec58-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="0ec58-113">assembly_id</span></span>|<span data-ttu-id="0ec58-114">Identificatore definito per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec58-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="0ec58-115">Questo numero viene assegnato a tutti gli oggetti relativi allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="0ec58-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="0ec58-116">name</span><span class="sxs-lookup"><span data-stu-id="0ec58-116">name</span></span>|<span data-ttu-id="0ec58-117">Nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0ec58-117">The name of the object.</span></span>|  
|<span data-ttu-id="0ec58-118">file_id</span><span class="sxs-lookup"><span data-stu-id="0ec58-118">file_id</span></span>|<span data-ttu-id="0ec58-119">Numero che identifica ogni oggetto. Al primo oggetto associato a un valore `assembly_id` specifico viene assegnato il valore 1.</span><span class="sxs-lookup"><span data-stu-id="0ec58-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="0ec58-120">Se più oggetti sono associati allo stesso valore `assembly_id`, ogni valore `file_id` successivo verrà incrementato di 1.</span><span class="sxs-lookup"><span data-stu-id="0ec58-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="0ec58-121">contenuto</span><span class="sxs-lookup"><span data-stu-id="0ec58-121">content</span></span>|<span data-ttu-id="0ec58-122">Rappresentazione esadecimale dell'assembly o del file.</span><span class="sxs-lookup"><span data-stu-id="0ec58-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="0ec58-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0ec58-123">In This Section</span></span>  
 [<span data-ttu-id="0ec58-124">Creazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="0ec58-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="0ec58-125">Viene descritta la creazione di assembly CLR SAFE, EXTERNAL_ACCESS e UNSAFE in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ec58-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="0ec58-126">Modifica di un assembly</span><span class="sxs-lookup"><span data-stu-id="0ec58-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="0ec58-127">Viene descritto l'aggiornamento di assembly CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ec58-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="0ec58-128">Eliminazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="0ec58-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="0ec58-129">Viene descritta l'eliminazione di assembly CLR da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ec58-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec58-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec58-130">See Also</span></span>  
 <span data-ttu-id="0ec58-131">[Sicurezza dell'integrazione con CLR](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="0ec58-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="0ec58-132">Sicurezza da accesso di codice dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="0ec58-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
