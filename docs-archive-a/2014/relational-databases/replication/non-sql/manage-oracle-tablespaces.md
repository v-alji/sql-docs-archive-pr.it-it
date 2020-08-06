---
title: Gestire spazi di tabella Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717922"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="bfcfb-102">Gestione di spazi di tabella Oracle</span><span class="sxs-lookup"><span data-stu-id="bfcfb-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="bfcfb-103">Uno spazio di tabella è un'unità di archiviazione di database approssimativamente equivalente a un filegroup in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfcfb-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bfcfb-104">Gli spazi di tabella consentono l'archiviazione e la gestione di oggetti di database all'interno di singoli gruppi.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="bfcfb-105">Per ulteriori informazioni, vedere la documentazione di Oracle.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="bfcfb-106">Quando si configura una tabella nell'ambito di una pubblicazione Oracle, è possibile specificare facoltativamente uno spazio di tabella Oracle esistente da utilizzare nell'archiviazione di informazioni di registrazione delle repliche.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="bfcfb-107">Se non specificato, lo spazio di tabella per gli oggetti di replica corrisponde allo spazio di tabella predefinito associato allo schema utente di amministrazione della replica che è stato configurato al momento della configurazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="bfcfb-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="bfcfb-108">**Per specificare uno spazio di tabella per una tabella di registrazione degli articoli**:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="bfcfb-109">Specificare uno spazio di tabella nella finestra di dialogo **Proprietà articolo** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="bfcfb-110">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bfcfb-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="bfcfb-111">Usare [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bfcfb-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="bfcfb-112">Per utilizzare **sp_changearticle**, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bfcfb-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="bfcfb-113">Nome del server di pubblicazione Oracle per il parametro **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="bfcfb-114">Nome della pubblicazione Oracle per il parametro **@publication** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="bfcfb-115">Nome dell'articolo per il parametro **@article** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="bfcfb-116">Valore "tablespace" per il parametro **@property** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="bfcfb-117">Nome dello spazio di tabella per il parametro **@value** .</span><span class="sxs-lookup"><span data-stu-id="bfcfb-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfcfb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfcfb-118">See Also</span></span>  
 <span data-ttu-id="bfcfb-119">[Configurare un server di pubblicazione Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="bfcfb-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="bfcfb-120">Oggetti creati nel server di pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="bfcfb-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
