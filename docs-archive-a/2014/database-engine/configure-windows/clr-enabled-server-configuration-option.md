---
title: Opzione di configurazione del server clr enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624356"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="bfee7-102">Opzione di configurazione del server clr enabled</span><span class="sxs-lookup"><span data-stu-id="bfee7-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="bfee7-103">Utilizzare l'opzione clr enabled per specificare se gli assembly utente possono essere eseguiti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfee7-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bfee7-104">L'opzione clr enabled restituisce i valori riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="bfee7-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="bfee7-105">Valore</span><span class="sxs-lookup"><span data-stu-id="bfee7-105">Value</span></span>|<span data-ttu-id="bfee7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfee7-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bfee7-107">0</span><span class="sxs-lookup"><span data-stu-id="bfee7-107">0</span></span>|<span data-ttu-id="bfee7-108">Esecuzione degli assembly non consentita in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfee7-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="bfee7-109">1</span><span class="sxs-lookup"><span data-stu-id="bfee7-109">1</span></span>|<span data-ttu-id="bfee7-110">Esecuzione degli assembly consentita in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfee7-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="bfee7-111">I server WOW64 devono essere riavviati prima che le modifiche apportate a questa impostazione diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="bfee7-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="bfee7-112">Il riavvio non è necessario per altri tipi di server.</span><span class="sxs-lookup"><span data-stu-id="bfee7-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfee7-113">Quando si esegue RECONFIGURE e il valore dell'opzione clr enabled viene modificato da 1 a 0, vengono scaricati immediatamente tutti i domini applicazione contenenti assembly utente.</span><span class="sxs-lookup"><span data-stu-id="bfee7-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfee7-114">L'esecuzione di CLR (Common Language Runtime) non è supportata nell'ambito dell'opzione lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="bfee7-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="bfee7-115">Disabilitare una delle due opzioni, "clr enabled" o "lightweight pooling".</span><span class="sxs-lookup"><span data-stu-id="bfee7-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="bfee7-116">Tra le funzionalità basate su CLR che non funzionano correttamente in modalità fiber sono inclusi il tipo di dati `hierarchy`, la replica e la gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="bfee7-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfee7-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfee7-117">Example</span></span>  
 <span data-ttu-id="bfee7-118">Nell'esempio seguente viene prima visualizzata l'impostazione corrente dell'opzione clr enabled, quindi abilitata l'opzione impostandone il valore su 1.</span><span class="sxs-lookup"><span data-stu-id="bfee7-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="bfee7-119">Per disabilitare l'opzione, impostare il valore su 0.</span><span class="sxs-lookup"><span data-stu-id="bfee7-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfee7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfee7-120">See Also</span></span>  
 <span data-ttu-id="bfee7-121">[Opzione di configurazione del server lightweight pooling](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="bfee7-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="bfee7-122">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bfee7-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="bfee7-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bfee7-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="bfee7-124">Opzione di configurazione del server lightweight pooling</span><span class="sxs-lookup"><span data-stu-id="bfee7-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
