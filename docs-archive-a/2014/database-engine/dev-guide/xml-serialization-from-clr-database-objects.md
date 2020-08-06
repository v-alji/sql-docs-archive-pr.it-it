---
title: Serializzazione XML da oggetti di database CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716655"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="00815-102">Serializzazione XML da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="00815-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="00815-103">La serializzazione XML è necessaria in due scenari:</span><span class="sxs-lookup"><span data-stu-id="00815-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="00815-104">Richiamo di servizi Web da oggetti CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="00815-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="00815-105">Conversione in XML di un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="00815-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="00815-106">Se la serializzazione XML viene eseguita richiamando la classe `XmlSerializer` di solito viene generato un assembly di serializzazione aggiuntivo che viene sottoposto a overload nel progetto con l'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="00815-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="00815-107">Tuttavia, per motivi di sicurezza, questo overload è disabilitato in CLR.</span><span class="sxs-lookup"><span data-stu-id="00815-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="00815-108">Pertanto, per chiamare un servizio Web o per eseguire la conversione da UDT a XML all'interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario creare manualmente l'assembly usando uno strumento denominato **Sgen.exe** fornito con l'.NET Framework che genera gli assembly di serializzazione necessari.</span><span class="sxs-lookup"><span data-stu-id="00815-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="00815-109">Quando si richiama `XmlSerializer`, l'assembly di serializzazione deve essere creato manualmente tramite la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="00815-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="00815-110">Eseguire lo strumento **Sgen.exe** fornito con .NET Framework SDK per creare l'assembly contenente i serializzatori XML per l'assembly di origine.</span><span class="sxs-lookup"><span data-stu-id="00815-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="00815-111">Utilizzando l'istruzione `CREATE ASSEMBLY`, registrare in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l'assembly generato.</span><span class="sxs-lookup"><span data-stu-id="00815-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="00815-112">Per informazioni sugli errori che possono verificarsi quando si esegue la serializzazione XML, vedere l'articolo supporto tecnico Microsoft seguente: ["Impossibile caricare l'assembly di serializzazione generato in modo dinamico"](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="00815-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="00815-113">Per informazioni su tipi di dati che non sono supportati da XMLSerializer, vedere Supporto dell'associazione a XML Schema nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00815-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00815-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00815-114">See Also</span></span>  
 <span data-ttu-id="00815-115">[Accesso ai dati da oggetti di database CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="00815-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="00815-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="00815-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
