---
title: Impostare le opzioni di crittografia nei server di destinazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636530"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="8a8da-102">Impostazione delle opzioni di crittografia nei server di destinazione</span><span class="sxs-lookup"><span data-stu-id="8a8da-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="8a8da-103">Se non è possibile utilizzare un certificato per le comunicazioni crittografate SSL (Secure Sockets Layer) tra server master e alcuni o tutti i server di destinazione e si desidera crittografare il canale di comunicazione, configurare i server di destinazione per l'utilizzo del livello di sicurezza necessario.</span><span class="sxs-lookup"><span data-stu-id="8a8da-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="8a8da-104">Per configurare il livello di sicurezza appropriato necessario per uno specifico canale di comunicazione tra server master e server di destinazione, impostare la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sottochiave del registro di sistema dell'agente \*\*\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ \*\* \<*instance_name*> **\SQLServerAgent\MsxEncryptChannelOptions (REG_DWORD)** nel server di destinazione su uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a8da-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="8a8da-105">Il valore di \<*instance_name*> è **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="8a8da-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="8a8da-106">Ad esempio, **MSSQL.1** o **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="8a8da-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="8a8da-107">valore</span><span class="sxs-lookup"><span data-stu-id="8a8da-107">Value</span></span>|<span data-ttu-id="8a8da-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a8da-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a8da-109">**0**</span><span class="sxs-lookup"><span data-stu-id="8a8da-109">**0**</span></span>|<span data-ttu-id="8a8da-110">Disabilita la crittografia tra il server di destinazione e il server master.</span><span class="sxs-lookup"><span data-stu-id="8a8da-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="8a8da-111">Selezionare questa opzione solo quando il canale tra il server di destinazione e il server master è protetto in altro modo.</span><span class="sxs-lookup"><span data-stu-id="8a8da-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="8a8da-112">**1**</span><span class="sxs-lookup"><span data-stu-id="8a8da-112">**1**</span></span>|<span data-ttu-id="8a8da-113">Attiva solo la crittografia tra il server di destinazione e il server master senza la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="8a8da-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="8a8da-114">**2**</span><span class="sxs-lookup"><span data-stu-id="8a8da-114">**2**</span></span>|<span data-ttu-id="8a8da-115">Attiva la crittografia SSL completa, inclusa la convalida del certificato, tra il server di destinazione e il server master.</span><span class="sxs-lookup"><span data-stu-id="8a8da-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="8a8da-116">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8a8da-116">This setting is the default.</span></span> <span data-ttu-id="8a8da-117">A meno che non ci siano motivi specifici per scegliere un valore diverso, è consigliabile non modificarla.</span><span class="sxs-lookup"><span data-stu-id="8a8da-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="8a8da-118">Se si specifica **1** o **2** , è necessario attivare la crittografia SSL sia nel server master sia nei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8a8da-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="8a8da-119">Se si specifica **2** , è necessario che nel server master sia presente un certificato firmato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a8da-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a8da-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a8da-120">See Also</span></span>  
 [<span data-ttu-id="8a8da-121">Abilitazione di connessioni crittografate al motore di database &#40;Gestione configurazione SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8a8da-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
