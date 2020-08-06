---
title: Utilizzo di oggetti di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723671"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="776e3-102">Utilizzo degli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="776e3-102">Working with Database Objects</span></span>
  <span data-ttu-id="776e3-103">Le fasi di creazione di un oggetto SMO sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="776e3-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="776e3-104">Creare un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="776e3-105">Impostare le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="776e3-106">Creare istanze degli oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="776e3-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="776e3-107">Impostare le proprietà degli oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="776e3-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="776e3-108">Creare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-108">Create the object.</span></span>  
  
 <span data-ttu-id="776e3-109">Quando vengono create istanze degli oggetti SMO in un'applicazione SMO, queste non esistono nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fino a che non viene chiamato il metodo `Create`.</span><span class="sxs-lookup"><span data-stu-id="776e3-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="776e3-110">Non è tuttavia necessario chiamare un metodo `Create` per ogni singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="776e3-111">Se per un oggetto è presente un set di oggetti figlio, per eseguire il metodo `Create` è necessario solo l'oggetto padre.</span><span class="sxs-lookup"><span data-stu-id="776e3-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="776e3-112">Per definire una tabella, ad esempio, è necessario che questa contenga almeno una colonna.</span><span class="sxs-lookup"><span data-stu-id="776e3-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="776e3-113">Una colonna inoltre non può esistere senza una tabella.</span><span class="sxs-lookup"><span data-stu-id="776e3-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="776e3-114">Esiste una relazione di interdipendenza tra la tabella e le rispettive colonne.</span><span class="sxs-lookup"><span data-stu-id="776e3-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="776e3-115">Il metodo <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> consente di apportare modifiche a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="776e3-116">Diverse modifiche a un oggetto, ad esempio l'aggiunta di oggetti figlio a una delle raccolte dell'oggetto o la modifica di un valore di proprietà, vengono eseguite in batch come modifica unica.</span><span class="sxs-lookup"><span data-stu-id="776e3-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="776e3-117">Il metodo `Alter` riduce traffico di rete e migliora complessivamente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="776e3-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="776e3-118">L'istruzione `Drop` viene utilizzata per rimuovere un oggetto e tutti i rispettivi oggetti figlio interdipendenti necessari per creare inizialmente l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="776e3-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776e3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="776e3-119">See Also</span></span>  
 [<span data-ttu-id="776e3-120">Modello a oggetti SMO</span><span class="sxs-lookup"><span data-stu-id="776e3-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
