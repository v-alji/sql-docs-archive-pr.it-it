---
title: Opzione di configurazione del server c2 audit mode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724187"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="737c9-102">Opzione di configurazione del server c2 audit mode</span><span class="sxs-lookup"><span data-stu-id="737c9-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="737c9-103">È possibile configurare l'opzione C2 audit mode tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o con l'opzione **c2 audit mode** in **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="737c9-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="737c9-104">Questa opzione consente di configurare il server per la registrazione dei tentativi di accesso alle istruzioni e agli oggetti riusciti e non riusciti.</span><span class="sxs-lookup"><span data-stu-id="737c9-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="737c9-105">Tali informazioni risultano utili per documentare l'attività del server e per tenere traccia delle possibili violazioni dei criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="737c9-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="737c9-106">Lo standard di sicurezza C2 è stato sostituito dalla certificazione con criteri comuni.</span><span class="sxs-lookup"><span data-stu-id="737c9-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="737c9-107">Vedere [Opzione di configurazione del server common criteria compliance enabled](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="737c9-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="737c9-108">File di log di controllo</span><span class="sxs-lookup"><span data-stu-id="737c9-108">Audit Log File</span></span>  
 <span data-ttu-id="737c9-109">I dati impostati tramite l'opzione C2 audit mode vengono salvati in un file nella directory predefinita dei dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="737c9-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="737c9-110">Se la dimensione del file raggiunge il limite di 200 megabyte (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea un nuovo file, chiude il vecchio file e scrive tutti i nuovi record di controllo nel nuovo file.</span><span class="sxs-lookup"><span data-stu-id="737c9-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="737c9-111">Il processo continua fino al riempimento della directory dei dati di controllo o alla disabilitazione della funzione di controllo.</span><span class="sxs-lookup"><span data-stu-id="737c9-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="737c9-112">Per determinare lo stato di una traccia C2, eseguire una query sulla vista del catalogo sys.traces.</span><span class="sxs-lookup"><span data-stu-id="737c9-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="737c9-113">L'opzione c2 audit mode consente di salvare una grande quantità di informazioni nel file di log, che può raggiungere rapidamente dimensioni notevoli.</span><span class="sxs-lookup"><span data-stu-id="737c9-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="737c9-114">Se non è più disponibile spazio nella directory in cui vengono salvati i log, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si chiuderà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="737c9-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="737c9-115">Se per la funzione di controllo è impostato l'avvio automatico, è necessario riavviare l'istanza con il flag **-f** (che ignora la funzione di controllo) oppure liberare spazio su disco per il log di controllo.</span><span class="sxs-lookup"><span data-stu-id="737c9-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="737c9-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="737c9-116">Permissions</span></span>  
 <span data-ttu-id="737c9-117">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="737c9-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="737c9-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="737c9-118">Example</span></span>  
 <span data-ttu-id="737c9-119">Nell'esempio seguente viene abilitata l'opzione C2 audit mode.</span><span class="sxs-lookup"><span data-stu-id="737c9-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="737c9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="737c9-120">See Also</span></span>  
 <span data-ttu-id="737c9-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="737c9-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="737c9-122">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="737c9-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="737c9-123">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="737c9-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
