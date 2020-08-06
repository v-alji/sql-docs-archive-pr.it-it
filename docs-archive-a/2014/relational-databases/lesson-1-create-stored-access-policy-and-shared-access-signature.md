---
title: Lezione 2. Creare un criterio per il contenitore e generare una chiave di firma di accesso condiviso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723848"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="88960-103">Lezione 2.</span><span class="sxs-lookup"><span data-stu-id="88960-103">Lesson 2.</span></span> <span data-ttu-id="88960-104">creare i criteri per il contenitore e generare una chiave di firma di accesso condivisa (SAS, Shared Access Signature)</span><span class="sxs-lookup"><span data-stu-id="88960-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="88960-105">In questa lezione, verrà illustrato come creare criteri del contenitore BLOB e generare una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="88960-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="88960-106">I criteri di accesso archiviati forniscono un livello di controllo aggiuntivo sulle firme di accesso condivise sul lato server.</span><span class="sxs-lookup"><span data-stu-id="88960-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="88960-107">Una firma di accesso condivisa è un URI che concede diritti di accesso limitati a contenitori, BLOB, code e tabelle.</span><span class="sxs-lookup"><span data-stu-id="88960-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="88960-108">Quando si utilizza questa nuova funzionalità avanzata, è necessario creare i criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="88960-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="88960-109">È possibile creare i criteri e una firma di accesso condivisa utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="88960-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="88960-110">Operazioni dell'API REST di Azure: [create container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx)e [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="88960-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="88960-111">[Metodo CloudBlobContainer. GetSharedAccessSignature](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="88960-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="88960-112">Uno strumento di Azure Explorer di terze parti, ad esempio [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="88960-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="88960-113">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="88960-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="88960-114">Lezione 3: Creare le credenziali di SQL Server</span><span class="sxs-lookup"><span data-stu-id="88960-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
