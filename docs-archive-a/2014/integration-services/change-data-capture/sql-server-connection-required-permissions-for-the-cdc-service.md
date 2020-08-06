---
title: Autorizzazioni necessarie per la connessione a SQL per il servizio CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627341"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="6adb4-102">Autorizzazioni necessarie per la connessione a SQL per il servizio CDC</span><span class="sxs-lookup"><span data-stu-id="6adb4-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="6adb4-103">Per eseguire le attività, CDC Service Configuration Console richiede informazioni di connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adb4-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="6adb4-104">In questo argomento vengono illustrate le informazioni che è possibile specificare nella finestra di dialogo Connect to SQL Server per l'impostazione della connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6adb4-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6adb4-105">La finestra di dialogo Connect to SQL Server viene visualizzata quando necessario, ad esempio quando le informazioni di connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sono disponibili o quando le informazioni sono presenti, ma la connessione non dispone delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="6adb4-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="6adb4-106">Nella tabella seguente vengono descritte le diverse attività per le quali è necessario disporre di una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e le autorizzazioni necessarie relative all'utente o all'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adb4-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="6adb4-107">Attività</span><span class="sxs-lookup"><span data-stu-id="6adb4-107">Task</span></span>|<span data-ttu-id="6adb4-108">Autorizzazioni minime</span><span class="sxs-lookup"><span data-stu-id="6adb4-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="6adb4-109">Preparare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adb4-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="6adb4-110">`dbcreator` Ruolo predefinito del server</span><span class="sxs-lookup"><span data-stu-id="6adb4-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="6adb4-111">Creare un account di accesso del servizio Oracle CDC-SQL Server che verrà utilizzato dal servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="6adb4-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="6adb4-112">`public` Ruolo predefinito del server</span><span class="sxs-lookup"><span data-stu-id="6adb4-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="6adb4-113">Creare un account di accesso del servizio Oracle CDC da utilizzare per la registrazione del nuovo servizio in MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="6adb4-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="6adb4-114">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="6adb4-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="6adb4-115">Modificare un account di accesso del servizio Oracle CDC da utilizzare per l'aggiornamento della registrazione del servizio in MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="6adb4-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="6adb4-116">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="6adb4-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="6adb4-117">Eliminare un account di accesso del servizio Oracle CDC da utilizzare per l'aggiornamento della registrazione del servizio in MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="6adb4-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="6adb4-118">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="6adb4-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6adb4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6adb4-119">See Also</span></span>  
 <span data-ttu-id="6adb4-120">[Connessione a SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6adb4-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="6adb4-121">Connessione a SQL Server per l'eliminazione</span><span class="sxs-lookup"><span data-stu-id="6adb4-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
