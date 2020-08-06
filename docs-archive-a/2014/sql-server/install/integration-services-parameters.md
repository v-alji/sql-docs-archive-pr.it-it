---
title: Parametri Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724407"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="30091-102">Parametri di Integration Services</span><span class="sxs-lookup"><span data-stu-id="30091-102">Integration Services Parameters</span></span>
  <span data-ttu-id="30091-103">Per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , è possibile decidere di analizzare i [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pacchetti nel computer o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] i file del pacchetto nel file System.</span><span class="sxs-lookup"><span data-stu-id="30091-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="30091-104">Se si sceglie di analizzare i file nel file system, specificare il percorso della cartella che contiene i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30091-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30091-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="30091-105">Options</span></span>  
 <span data-ttu-id="30091-106">**Analizza pacchetti SSIS nel computer**</span><span class="sxs-lookup"><span data-stu-id="30091-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="30091-107">Selezionare questa opzione per analizzare i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nel computer.</span><span class="sxs-lookup"><span data-stu-id="30091-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="30091-108">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30091-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="30091-109">**Analizza file pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="30091-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="30091-110">Selezionare questa opzione per analizzare i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nel file system.</span><span class="sxs-lookup"><span data-stu-id="30091-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="30091-111">**Percorso pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="30091-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="30091-112">Individuare il percorso UNC o locale in cui sono memorizzati i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30091-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="30091-113">Non è necessario includere i nomi di file.</span><span class="sxs-lookup"><span data-stu-id="30091-113">You do not have to include file names.</span></span> <span data-ttu-id="30091-114">Se il percorso immesso non è accessibile, non è possibile fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30091-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="30091-115">Per impostazione predefinita, il percorso è vuoto.</span><span class="sxs-lookup"><span data-stu-id="30091-115">By default, the path is blank.</span></span> <span data-ttu-id="30091-116">Questo campo è abilitato solo quando si seleziona **Analizza file di pacchetto SSIS**.</span><span class="sxs-lookup"><span data-stu-id="30091-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30091-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30091-117">See Also</span></span>  
 <span data-ttu-id="30091-118">[Utilizzo di preparazione aggiornamento](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="30091-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="30091-119">Guida di riferimento all'interfaccia utente di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="30091-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
