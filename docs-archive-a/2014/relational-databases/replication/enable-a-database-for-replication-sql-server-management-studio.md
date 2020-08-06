---
title: Abilitare un database per la replica (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624614"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="98f8e-102">Abilitazione di un database per la replica (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="98f8e-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="98f8e-103">Un database viene implicitamente abilitato per la replica quando un membro del ruolo predefinito del server **sysadmin** crea una pubblicazione mediante la Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="98f8e-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="98f8e-104">Il membro del ruolo predefinito del server **sysadmin** può inoltre abilitare esplicitamente un database per la replica, in modo che un membro del ruolo predefinito del database **db_owner** possa creare una o più pubblicazioni in tale database.</span><span class="sxs-lookup"><span data-stu-id="98f8e-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="98f8e-105">A tale scopo, usare la pagina **Database di pubblicazione** della finestra di dialogo **Proprietà server di pubblicazione - \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="98f8e-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="98f8e-106">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="98f8e-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="98f8e-107">Per abilitare un database per la replica</span><span class="sxs-lookup"><span data-stu-id="98f8e-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="98f8e-108">Nella pagina **Database di pubblicazione** della finestra di dialogo **Proprietà server di pubblicazione - \<Publisher>** selezionare la casella di controllo **Transazionale** e/o **Merge** per ogni database da replicare.</span><span class="sxs-lookup"><span data-stu-id="98f8e-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="98f8e-109">Selezionare **Transazionale** per abilitare il database per la replica snapshot.</span><span class="sxs-lookup"><span data-stu-id="98f8e-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
