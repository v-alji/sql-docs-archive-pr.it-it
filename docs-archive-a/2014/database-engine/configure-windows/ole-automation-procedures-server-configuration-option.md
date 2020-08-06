---
title: Opzione di configurazione del server Ole Automation Procedures | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712363"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="e1345-102">Opzione di configurazione del server Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="e1345-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="e1345-103">Utilizzare l'opzione `Ole Automation Procedures` per specificare se è possibile creare un'istanza degli oggetti di automazione OLE all'interno di batch [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1345-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="e1345-104">Questa opzione può essere configurata usando anche la gestione basata su criteri o la stored procedure **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="e1345-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="e1345-105">Per ulteriori informazioni, vedere [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e1345-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="e1345-106">L'opzione `Ole Automation Procedures` può essere impostata su uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="e1345-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="e1345-107">0</span><span class="sxs-lookup"><span data-stu-id="e1345-107">0</span></span>  
 <span data-ttu-id="e1345-108">L'opzione Ole Automation Procedures è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e1345-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="e1345-109">Impostazione predefinita per le nuove istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1345-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e1345-110">1</span><span class="sxs-lookup"><span data-stu-id="e1345-110">1</span></span>  
 <span data-ttu-id="e1345-111">L'opzione Ole Automation Procedures è abilitata.</span><span class="sxs-lookup"><span data-stu-id="e1345-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="e1345-112">Quando l'opzione Ole Automation Procedures è abilitata, l'ambiente di esecuzione condiviso OLE viene avviato mediante una chiamata a **sp_OACreate** .</span><span class="sxs-lookup"><span data-stu-id="e1345-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="e1345-113">Il valore corrente dell' `Ole Automation Procedures` opzione può essere visualizzato e modificato utilizzando il **sp_configure** stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="e1345-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e1345-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="e1345-114">Examples</span></span>  
 <span data-ttu-id="e1345-115">Nell'esempio seguente viene illustrata la procedura per la visualizzazione dell'impostazione corrente dell'opzione Ole Automation Procedures.</span><span class="sxs-lookup"><span data-stu-id="e1345-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="e1345-116">Nell'esempio seguente viene illustrata la procedura per l'abilitazione dell'opzione Ole Automation Procedures.</span><span class="sxs-lookup"><span data-stu-id="e1345-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1345-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1345-117">See Also</span></span>  
 <span data-ttu-id="e1345-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e1345-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="e1345-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e1345-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="e1345-120">[Configurazione superficie di attacco](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e1345-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="e1345-121">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1345-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
