---
title: Concedere le autorizzazioni per il servizio Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624839"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="6c816-102">Concessione di autorizzazioni al servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="6c816-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="6c816-103">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], per impostazione predefinita quando si installa [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tutti gli utenti nel gruppo Utenti dispongono di accesso al servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c816-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="6c816-104">Quando si installa la versione corrente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], gli utenti non dispongono di accesso al servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c816-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="6c816-105">Il servizio è protetto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6c816-105">The service is secure by default.</span></span> <span data-ttu-id="6c816-106">Dopo avere installato [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , l'amministratore deve concedere l'accesso al servizio.</span><span class="sxs-lookup"><span data-stu-id="6c816-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="6c816-107">Per concedere l'accesso al servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="6c816-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="6c816-108">Eseguire Dcomcnfg.exe.</span><span class="sxs-lookup"><span data-stu-id="6c816-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="6c816-109">Dcomcnfg.exe fornisce un'interfaccia utente per la modifica di determinate impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="6c816-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="6c816-110">Nella finestra di dialogo **Servizi componenti** espandere il nodo > Computer > Risorse del computer > Config DCOM.</span><span class="sxs-lookup"><span data-stu-id="6c816-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="6c816-111">Fare clic con il pulsante destro del mouse su **Microsoft SQL Server Integration Services 12,0**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6c816-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6c816-112">Nella scheda **Sicurezza** della finestra **Autorizzazioni di esecuzione e attivazione** fare clic su **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="6c816-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="6c816-113">Aggiungere utenti e assegnare le autorizzazioni appropriate, quindi scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="6c816-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="6c816-114">Ripetere i passaggi 4 e 5 per le autorizzazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="6c816-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="6c816-115">Riavviare SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6c816-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="6c816-116">Riavviare il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c816-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
