---
title: Elemento &lt;xsd:redefine&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719733"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="8ce6e-102">Elemento &lt;xsd:redefine&gt;</span><span class="sxs-lookup"><span data-stu-id="8ce6e-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="8ce6e-103">L'elemento **redefine** dello schema XSD W3C rende disponibile il supporto per la ridefinizione dei componenti di schema.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="8ce6e-104">Tuttavia, il supporto per questa direttiva è potenzialmente costoso per le prestazioni e richiede anche che vengano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rivalide tutte le istanze del `xml` tipo di dati associate allo schema ridefinito.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="8ce6e-105">Di conseguenza, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non supporta questo elemento.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="8ce6e-106">Gli XML Schema che includono l'elemento **\<xsd:redefine>** vengono rifiutati dal server.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="8ce6e-107">In alternativa, per aggiornare uno schema o i relativi componenti, è possibile eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="8ce6e-108">Creare una nuova raccolta XML Schema con i componenti di schema modificati.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="8ce6e-109">Riscrivere tutti i tipi di dati `xml` (XML DT) che usano la raccolta XML Schema da ridefinire per usare in sostituzione la nuova raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="8ce6e-110">A questo scopo, utilizzare l'opzione ALTER COLUMN del comando ALTER TABLE per riscrivere colonne o modificare i vincoli della raccolta XML Schema su variabili o parametri.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="8ce6e-111">Eliminare la versione obsoleta della raccolta XML Schema.</span><span class="sxs-lookup"><span data-stu-id="8ce6e-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce6e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce6e-112">See Also</span></span>  
 [<span data-ttu-id="8ce6e-113">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="8ce6e-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
