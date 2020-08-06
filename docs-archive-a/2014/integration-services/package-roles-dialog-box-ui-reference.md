---
title: Riferimento all'interfaccia utente della finestra di dialogo ruoli pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718557"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="3ac50-102">Riferimento all'interfaccia utente della finestra di dialogo Ruoli pacchetto</span><span class="sxs-lookup"><span data-stu-id="3ac50-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="3ac50-103">Usare la finestra di dialogo **Ruoli pacchetto** , disponibile in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], per specificare i ruoli a livello di database che dispongono dell'accesso in lettura al pacchetto e quelli che dispongono dell'accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="3ac50-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="3ac50-104">I ruoli a livello di database si applicano solo ai pacchetti archiviati nel database  **msdb** di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ac50-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="3ac50-105">Per altre informazioni sui ruoli a livello di database di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e le relative autorizzazioni, vedere [Ruoli Integration Services &#40;servizio SSIS&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="3ac50-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="3ac50-106">I ruoli elencati nella finestra di dialogo sono quelli attualmente disponibili nel database di sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="3ac50-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="3ac50-107">Se non viene selezionato alcun ruolo, viene applicato il ruolo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ac50-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="3ac50-108">Per impostazione predefinita, il ruolo lettura include **db_ssisadmin**, **db_ssisoperator**e l'utente che ha creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ac50-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="3ac50-109">Gli utenti membri di uno di questi ruoli o creatori dei pacchetti possono enumerare, visualizzare, esportare ed eseguire i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3ac50-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="3ac50-110">Per impostazione predefinita, il ruolo scrittura include **db_ssisadmin** e l'utente che ha creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ac50-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="3ac50-111">L'utente membro di questo ruolo e il creatore dei pacchetti possono importare, eliminare e modificare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3ac50-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="3ac50-112">La colonna **ownersid** nella tabella **sysssispackages** include l'ID di sicurezza (SID) univoco dell'utente che ha creato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ac50-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3ac50-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3ac50-113">Options</span></span>  
 <span data-ttu-id="3ac50-114">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="3ac50-114">**Package Name**</span></span>  
 <span data-ttu-id="3ac50-115">Consente di specificare il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ac50-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="3ac50-116">**Ruolo lettura**</span><span class="sxs-lookup"><span data-stu-id="3ac50-116">**Reader Role**</span></span>  
 <span data-ttu-id="3ac50-117">Consente di selezionare un ruolo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3ac50-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="3ac50-118">**Ruolo scrittura**</span><span class="sxs-lookup"><span data-stu-id="3ac50-118">**Writer Role**</span></span>  
 <span data-ttu-id="3ac50-119">Consente di selezionare un ruolo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3ac50-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac50-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac50-120">See Also</span></span>  
 <span data-ttu-id="3ac50-121">[Ruoli a livello di database](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="3ac50-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="3ac50-122">Panoramica sulla sicurezza &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ac50-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
