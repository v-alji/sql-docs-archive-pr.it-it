---
title: Database di pubblicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624054"
---
# <a name="publication-database"></a><span data-ttu-id="8d3ce-102">Database di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="8d3ce-102">Publication Database</span></span>
  <span data-ttu-id="8d3ce-103">Il database di pubblicazione è il database del server di pubblicazione che funge da origine dei dati e degli oggetti di database da replicare.</span><span class="sxs-lookup"><span data-stu-id="8d3ce-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="8d3ce-104">Tutti i database utilizzati nella replica devono essere abilitati.</span><span class="sxs-lookup"><span data-stu-id="8d3ce-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="8d3ce-105">Il database viene abilitato quando un membro del ruolo predefinito del server **sysadmin** :</span><span class="sxs-lookup"><span data-stu-id="8d3ce-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="8d3ce-106">Crea una pubblicazione nel database tramite la Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8d3ce-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="8d3ce-107">Seleziona il database nella finestra di dialogo **Proprietà server di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="8d3ce-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="8d3ce-108">Esegue **sp_replicationdboption** e imposta su **True** l'opzione per la **pubblicazione** relativa a snapshot e pubblicazioni transazionali o l'opzione per la **pubblicazione di tipo merge**relativa a pubblicazioni di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="8d3ce-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d3ce-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8d3ce-109">Options</span></span>  
 <span data-ttu-id="8d3ce-110">**Database**</span><span class="sxs-lookup"><span data-stu-id="8d3ce-110">**Databases**</span></span>  
 <span data-ttu-id="8d3ce-111">Consente di selezionare il nome del database contenente i dati e gli oggetti di database che si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="8d3ce-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d3ce-112">See Also</span></span>  
 <span data-ttu-id="8d3ce-113">[Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="8d3ce-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="8d3ce-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="8d3ce-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="8d3ce-115">[Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8d3ce-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="8d3ce-116">sp_replicationdboption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8d3ce-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
