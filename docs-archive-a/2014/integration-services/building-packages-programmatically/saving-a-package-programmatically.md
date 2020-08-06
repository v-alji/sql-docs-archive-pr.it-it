---
title: Salvataggio di un pacchetto a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626847"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="020e0-102">Salvataggio di un pacchetto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="020e0-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="020e0-103">Dopo avere compilato un nuovo pacchetto a livello di programmazione, o dopo averne modificato uno esistente, si desidera in genere salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="020e0-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="020e0-104">Tutti i metodi utilizzati in questo argomento per salvare i pacchetti richiedono un riferimento all'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="020e0-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="020e0-105">Dopo aver aggiunto il riferimento in un nuovo progetto, importare lo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> con un'istruzione `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="020e0-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="020e0-106">Salvataggio di un pacchetto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="020e0-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="020e0-107">Per salvare un pacchetto a livello di programmazione, chiamare uno dei metodi seguenti della classe [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] di <xref:Microsoft.SqlServer.Dts.Runtime.Application>:</span><span class="sxs-lookup"><span data-stu-id="020e0-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="020e0-108">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="020e0-108">Storage Location</span></span>|<span data-ttu-id="020e0-109">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="020e0-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="020e0-110">File</span><span class="sxs-lookup"><span data-stu-id="020e0-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="020e0-111">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="020e0-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="020e0-112">o</span><span class="sxs-lookup"><span data-stu-id="020e0-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="020e0-113">I metodi della classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> per l'utilizzo dell'archivio pacchetti SSIS supportano solo "." o il nome del server locale.</span><span class="sxs-lookup"><span data-stu-id="020e0-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="020e0-114">Non è possibile utilizzare "(local)" o "localhost".</span><span class="sxs-lookup"><span data-stu-id="020e0-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="020e0-115">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="020e0-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="020e0-116">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="020e0-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="020e0-117">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="020e0-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="020e0-118">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="020e0-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020e0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="020e0-119">See Also</span></span>  
 [<span data-ttu-id="020e0-120">Salvataggio di pacchetti</span><span class="sxs-lookup"><span data-stu-id="020e0-120">Save Packages</span></span>](../save-packages.md)  
  
  
