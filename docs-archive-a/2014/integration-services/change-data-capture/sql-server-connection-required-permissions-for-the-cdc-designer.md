---
title: Autorizzazioni necessarie della connessione di SQL Server per la finestra di progettazione di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624285"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="dc028-102">Autorizzazioni necessarie della connessione di SQL Server per la finestra di progettazione di CDC</span><span class="sxs-lookup"><span data-stu-id="dc028-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="dc028-103">Per eseguire attività in CDC Designer Console è necessario specificare le informazioni di connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc028-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="dc028-104">In questo argomento vengono illustrate le informazioni che è possibile specificare nella finestra di dialogo **Connect to SQL Server** per l'impostazione della connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc028-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dc028-105">La finestra di dialogo **Connect to SQL Server** viene visualizzata quando necessario, ad esempio quando le informazioni di connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sono disponibili o quando le informazioni sono presenti, ma la connessione non dispone delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="dc028-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="dc028-106">Nella tabella seguente vengono descritte le diverse attività per le quali è necessario disporre di una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e le autorizzazioni necessarie relative all'utente o all'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc028-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="dc028-107">Attività</span><span class="sxs-lookup"><span data-stu-id="dc028-107">Task</span></span>|<span data-ttu-id="dc028-108">Autorizzazioni minime</span><span class="sxs-lookup"><span data-stu-id="dc028-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="dc028-109">Visualizzare l'elenco di servizi e istanze di CDC utilizzando l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associata.</span><span class="sxs-lookup"><span data-stu-id="dc028-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="dc028-110">`db_datareader` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dc028-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="dc028-111">Avviare/arrestare l'istanza di CDC)</span><span class="sxs-lookup"><span data-stu-id="dc028-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="dc028-112">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dc028-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="dc028-113">Visualizzare lo stato dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="dc028-113">View the CDC Instance status.</span></span>|<span data-ttu-id="dc028-114">`db_owner` per il database dell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="dc028-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="dc028-115">Creare un nuovo database dell'istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="dc028-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="dc028-116">`dbcreator` Ruolo predefinito del server</span><span class="sxs-lookup"><span data-stu-id="dc028-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="dc028-117">Creare una nuova istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="dc028-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="dc028-118">`db_datareader` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dc028-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="dc028-119">`db_owner` per il database CDC creato.</span><span class="sxs-lookup"><span data-stu-id="dc028-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="dc028-120">Ottenere gli script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dc028-120">Get deployment scripts.</span></span>|<span data-ttu-id="dc028-121">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dc028-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="dc028-122">`db_owner` per il database CDC correlato</span><span class="sxs-lookup"><span data-stu-id="dc028-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="dc028-123">Modificare la configurazione e aggiungere/rimuovere istanze di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="dc028-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="dc028-124">`db_datareader` e `db_datawriter` per MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="dc028-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="dc028-125">`db_owner` per il database CDC correlato</span><span class="sxs-lookup"><span data-stu-id="dc028-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc028-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc028-126">See Also</span></span>  
 <span data-ttu-id="dc028-127">[Accedere a CDC Designer Console](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="dc028-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="dc028-128">Connessione di SQL Server per la creazione dell'istanza</span><span class="sxs-lookup"><span data-stu-id="dc028-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
