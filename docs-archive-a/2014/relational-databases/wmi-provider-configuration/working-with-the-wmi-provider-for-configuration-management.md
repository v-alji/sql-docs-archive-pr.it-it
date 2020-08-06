---
title: Utilizzo del provider WMI per la gestione della configurazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80f311fb0abae2337f6ea4a5d5d85aaa0d320b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628545"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="09f86-102">Utilizzo del provider WMI per Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="09f86-102">Working with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="09f86-103">Prima di eseguire la programmazione con il provider WMI per Gestione computer, è necessario tenere presente quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="09f86-103">Consider the following before programming with the WMI Provider for Computer Management:</span></span>  
  
## <a name="binding"></a><span data-ttu-id="09f86-104">Binding</span><span class="sxs-lookup"><span data-stu-id="09f86-104">Binding</span></span>  
 <span data-ttu-id="09f86-105">Il provider WMI per Gestione configurazione è un modello a oggetti COM che supporta l'associazione anticipata e tardiva.</span><span class="sxs-lookup"><span data-stu-id="09f86-105">The WMI Provider for Configuration Management is a COM object model and it supports early and late binding.</span></span> <span data-ttu-id="09f86-106">Con l'associazione tardiva è possibile utilizzare linguaggi di scripting, come VBScript, per modificare a livello di codice gli alias, le impostazioni di rete e i servizi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09f86-106">With late binding you can use script languages, such as VBScript, to manipulate the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and aliases programmatically.</span></span>  
  
 <span data-ttu-id="09f86-107">Per ulteriori informazioni sulla programmazione di implementazioni del provider WMI utilizzando linguaggi di scripting, visitare il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [sito Web](https://go.microsoft.com/fwlink/?linkid=15426)MSDN.</span><span class="sxs-lookup"><span data-stu-id="09f86-107">For further information about programming WMI Provider implementations using scripting languages, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="09f86-108">Definizione di una stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="09f86-108">Specifying a Connection String</span></span>  
 <span data-ttu-id="09f86-109">Le applicazioni indirizzano il provider WMI per Gestione configurazione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connettendosi a uno spazio dei nomi WMI definito dal provider.</span><span class="sxs-lookup"><span data-stu-id="09f86-109">Applications direct the WMI Provider for Configuration Management to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="09f86-110">Il servizio Windows WMI esegue il mapping di questo spazio dei nomi alla DLL del provider e lo carica in memoria.</span><span class="sxs-lookup"><span data-stu-id="09f86-110">The Windows WMI service maps this namespace to the provider DLL and loads it into memory.</span></span> <span data-ttu-id="09f86-111">Tutte le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono rappresentate con un solo spazio dei nomi WMI.</span><span class="sxs-lookup"><span data-stu-id="09f86-111">All instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are represented with a single WMI namespace.</span></span> <span data-ttu-id="09f86-112">Lo spazio dei nomi predefinito è</span><span class="sxs-lookup"><span data-stu-id="09f86-112">The namespace defaults to</span></span>  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 <span data-ttu-id="09f86-113">dove `instance_name` corrisponde per impostazione predefinita a `MSSQLSERVER` in un'installazione predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09f86-113">where `instance_name` defaults to `MSSQLSERVER` in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="09f86-114">**Nota:** Se ci si connette tramite Windows Firewall sarà necessario assicurarsi che i computer siano configurati in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="09f86-114">**Note:** If you are connecting through Windows Firewall you will need to make sure your computers are configured appropriately.</span></span> <span data-ttu-id="09f86-115">Vedere l'articolo "connessione tramite Windows Firewall" nella documentazione di Strumentazione gestione Windows nel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [sito Web](https://go.microsoft.com/fwlink/?linkid=15426)MSDN.</span><span class="sxs-lookup"><span data-stu-id="09f86-115">See the "Connecting Through Windows Firewall" article in the Windows Management Instrumentation documentation on [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="09f86-116">Autorizzazioni e autenticazione del server</span><span class="sxs-lookup"><span data-stu-id="09f86-116">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="09f86-117">Per accedere al provider WMI per Gestione configurazione, è necessario che lo script di gestione WMI del client sia in esecuzione nel contesto di un amministratore nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09f86-117">To access the WMI Provider for Configuration Management, the client WMI management script must be running in the context of an administrator on the target computer.</span></span> <span data-ttu-id="09f86-118">È necessario essere membro del gruppo locale Administrators di Windows nel computer da gestire.</span><span class="sxs-lookup"><span data-stu-id="09f86-118">You need to be a member of the local Windows administrators group on the computer you want to manage.</span></span>  
  
 <span data-ttu-id="09f86-119">L'amministratore può impostare i criteri di gruppo per controllare l'accesso utente ai provider WMI.</span><span class="sxs-lookup"><span data-stu-id="09f86-119">The administrator can set group policies to control user access to WMI providers.</span></span> <span data-ttu-id="09f86-120">Per ulteriori informazioni sull'impostazione dei criteri di gruppo, vedere l'argomento relativo ai criteri di gruppo e a MMC nella Guida di Gestione configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09f86-120">For more information about setting group policies see "Group Policy and MMC" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help.</span></span>  
  
 <span data-ttu-id="09f86-121">Lo script di gestione WMI può essere utilizzato per aggiornare l'account con cui vengono eseguiti i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09f86-121">The WMI management script can be used to update the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services run.</span></span>  
  
 <span data-ttu-id="09f86-122">I certificati di sicurezza sono supportati dal provider WMI per Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="09f86-122">Security certificates are supported by the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="09f86-123">Per ulteriori informazioni sui certificati, vedere [gerarchia di crittografia](../security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="09f86-123">For more information about certificates, see [Encryption Hierarchy](../security/encryption/encryption-hierarchy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f86-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09f86-124">See Also</span></span>  
 [<span data-ttu-id="09f86-125">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="09f86-125">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
