---
title: Concetti relativi al provider WMI per la gestione della configurazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management
- SQL Server WMI Provider
- configuration management [WMI]
- WMI Provider for Configuration Management, about WMI Provider for Configuration Management
ms.assetid: 7e41db24-b915-4eb8-a1d6-e6948ee915b7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be0682e7d6de5cb8c3d67a2f300bb89122213652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626577"
---
# <a name="wmi-provider-for-configuration-management-concepts"></a><span data-ttu-id="93221-102">Concetti relativi al provider WMI per Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="93221-102">WMI Provider for Configuration Management Concepts</span></span>
  <span data-ttu-id="93221-103">Il provider WMI è un livello pubblicato utilizzato con lo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] snap-in Configuration Manager per [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) e il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="93221-103">The WMI provider is a published layer that is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager snap-in for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="93221-104">Viene fornita una modalità unificata per l'interfaccia con le chiamate API che gestiscono le operazioni del Registro di sistema richieste da Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e vengono offerte funzioni avanzate di controllo e manipolazione sui servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionati.</span><span class="sxs-lookup"><span data-stu-id="93221-104">It provides a unified way for interfacing with the API calls that manage the registry operations requested by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and provides enhanced control and manipulation over the selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span>  
  
 <span data-ttu-id="93221-105">Il provider WMI di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un file DLL e un file MOF, compilati automaticamente dal programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93221-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider is a DLL and a MOF file, which are compiled automatically by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="93221-106">Il provider WMI di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiene un set di classi di oggetti utilizzati per controllare i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attraverso i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="93221-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider contains a set of object classes used to control the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services using the following methods:</span></span>  
  
-   <span data-ttu-id="93221-107">Un linguaggio di scripting come VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)] o Perl, in cui è possibile incorporare Windows Query Language (WQL).</span><span class="sxs-lookup"><span data-stu-id="93221-107">A script language such as VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)], or Perl, in which Windows Query Language (WQL) can be embedded.</span></span>  
  
-   <span data-ttu-id="93221-108">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> in un programma di codice gestito SMO.</span><span class="sxs-lookup"><span data-stu-id="93221-108">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object in an SMO managed code program.</span></span>  
  
-   <span data-ttu-id="93221-109">Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o MMC con lo snap-in del provider WMI di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93221-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or MMC with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI provider snap-in.</span></span>  
  
## <a name="using-a-script-language"></a><span data-ttu-id="93221-110">Utilizzo di un linguaggio di scripting</span><span class="sxs-lookup"><span data-stu-id="93221-110">Using a Script Language</span></span>  
 <span data-ttu-id="93221-111">I vantaggi dell'utilizzo di un linguaggio di scripting sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="93221-111">The advantages of using a script language include the following:</span></span>  
  
-   <span data-ttu-id="93221-112">Non è necessario un ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="93221-112">A development environment is not required.</span></span>  
  
-   <span data-ttu-id="93221-113">I file che supportano il linguaggio di scripting sono ampiamente disponibili.</span><span class="sxs-lookup"><span data-stu-id="93221-113">The files that support the script language are widely available.</span></span>  
  
 <span data-ttu-id="93221-114">Lo script può funzionare anche con altri provider WMI oltre a quello di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93221-114">The script can also work with other WMI Providers in addition to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider.</span></span> <span data-ttu-id="93221-115">Un amministratore di dominio può utilizzare uno script per configurare i servizi, le impostazioni di rete e le impostazioni dell'alias in più computer di una rete.</span><span class="sxs-lookup"><span data-stu-id="93221-115">A domain administrator can use a script to set up the services, network settings, and alias settings on multiple computers on a network.</span></span>  
  
 <span data-ttu-id="93221-116">In questa sezione viene illustrato in modo più approfondito l'accesso al provider WMI per Gestione configurazione dagli script.</span><span class="sxs-lookup"><span data-stu-id="93221-116">This section deals with accessing the WMI Provider for Configuration Management from scripts in further detail.</span></span>  
  
## <a name="using-the-smo-managedcomputer-object"></a><span data-ttu-id="93221-117">Utilizzo dell'oggetto ManagedComputer SMO </span><span class="sxs-lookup"><span data-stu-id="93221-117">Using the SMO ManagedComputer Object</span></span>  
 <span data-ttu-id="93221-118">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> è un oggetto SMO gestito che consente di accedere al provider WMI per Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="93221-118">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object is a managed SMO object that provides access to the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="93221-119">Tramite un programma SMO, l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> può essere utilizzato per visualizzare e modificare i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le impostazioni di rete e le impostazioni dell'alias.</span><span class="sxs-lookup"><span data-stu-id="93221-119">By using an SMO program, the <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object can be used to view and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and alias settings.</span></span> <span data-ttu-id="93221-120">Per ulteriori informazioni, vedere [gestione dei servizi e delle impostazioni di rete tramite il provider WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="93221-120">For more information, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
## <a name="using-the-microsoft-management-console-or-sql-server-configuration-manager"></a><span data-ttu-id="93221-121">Utilizzo di Microsoft Management Console o Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="93221-121">Using the Microsoft Management Console or SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="93221-122">Microsoft Management Console (MMC) offre un'interfaccia per la gestione dei servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a differenza di un linguaggio di scripting o di un programma di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="93221-122">Microsoft Management Console (MMC) provides an interface to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, as opposed to a scripting language or managed code program.</span></span> <span data-ttu-id="93221-123">Lo snap-in MMC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere utilizzato per arrestare e avviare servizi e modificare gli account di servizio.</span><span class="sxs-lookup"><span data-stu-id="93221-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management MMC snap-in can be used to stop and start services, and to change service accounts.</span></span>  
  
 <span data-ttu-id="93221-124">Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere utilizzato anche per gestire protocolli client e server, alias del server e servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93221-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager can also be used to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, client and server protocols, and server aliases</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93221-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93221-125">See Also</span></span>  
 <span data-ttu-id="93221-126">[Informazioni sul provider WMI per la gestione della configurazione](understanding-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="93221-126">[Understanding the WMI Provider for Configuration Management](understanding-the-wmi-provider-for-configuration-management.md) </span></span>  
 <span data-ttu-id="93221-127">[Utilizzo del provider WMI per la gestione della configurazione](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="93221-127">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="93221-128">Uso di WQL e di linguaggi di scripting con il provider WMI per la gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="93221-128">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
