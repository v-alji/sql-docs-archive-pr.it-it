---
title: Creare un account Finance della dimensione di tipo padre-figlio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714680"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="3962f-102">Creare un conto finanziario della dimensione di tipo padre-figlio</span><span class="sxs-lookup"><span data-stu-id="3962f-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="3962f-103">In una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimensione di tipo conto è una dimensione i cui attributi rappresentano un grafico di account per la creazione di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="3962f-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="3962f-104">Una dimensione di tipo Conti consente di gestire in modo selettivo le modalità di aggregazione dei conti nel tempo.</span><span class="sxs-lookup"><span data-stu-id="3962f-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="3962f-105">Una dimensione di tipo Conti consente inoltre di utilizzare un meccanismo standard per risolvere la maggior parte dei problemi di aggregazione non standard che in genere di verificano nelle soluzione di Business Intelligence per la gestione dei dati finanziari.</span><span class="sxs-lookup"><span data-stu-id="3962f-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="3962f-106">Se non si disponesse di tale meccanismo standard, la risoluzione dei problemi di aggregazione non standard richiederebbe formule personalizzate di rollup, membri calcolati o script MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="3962f-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="3962f-107">Per identificare una dimensione come dimensione di tipo Conti, impostare la proprietà `Type` della dimensione su `Accounts`.</span><span class="sxs-lookup"><span data-stu-id="3962f-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="3962f-108">Struttura dimensione</span><span class="sxs-lookup"><span data-stu-id="3962f-108">Dimension Structure</span></span>  
 <span data-ttu-id="3962f-109">In una dimensione di tipo Conti sono contenuti almeno due attributi:</span><span class="sxs-lookup"><span data-stu-id="3962f-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="3962f-110">Attributo chiave, ovvero un attributo che identifica singoli account nella tabella delle dimensioni per la dimensione di tipo conti.</span><span class="sxs-lookup"><span data-stu-id="3962f-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="3962f-111">Un attributo dell'account, ovvero un attributo padre che descrive in che modo i conti vengono disposti in modo gerarchico nella dimensione di tipo conti.</span><span class="sxs-lookup"><span data-stu-id="3962f-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="3962f-112">Per identificare un attributo come attributo Conto, impostare la proprietà `Type` dell'attributo su `Account` e la proprietà `Usage` su `Parent`.</span><span class="sxs-lookup"><span data-stu-id="3962f-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="3962f-113">Facoltativamente, nelle dimensioni di tipo Conti possono essere contenuti gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3962f-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="3962f-114">Un attributo di tipo conto, ovvero un attributo che definisce il tipo di conto per ogni conto nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="3962f-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="3962f-115">Viene eseguito il mapping tra i nomi dei membri dell'attributo di tipo Conto e i tipi di conto definiti per il database o il progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e tali nomi indicano la funzione di aggregazione usata da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per tali conti.</span><span class="sxs-lookup"><span data-stu-id="3962f-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="3962f-116">È inoltre possibile utilizzare operatori unari o formule personalizzate di rollup per determinare le modalità di aggregazione per gli attributi Conto, ma gli attributi di tipo Conto consentono di applicare in modo semplice un comportamento consistente a un grafico dei conti senza che sia necessario apportare modifiche al database relazionale sottostante.</span><span class="sxs-lookup"><span data-stu-id="3962f-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="3962f-117">Per identificare un attributo di tipo Conto, impostare la proprietà `Type` dell'attributo su `AccountType`.</span><span class="sxs-lookup"><span data-stu-id="3962f-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="3962f-118">Un attributo del nome dell'account, ovvero un attributo usato per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="3962f-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="3962f-119">Per identificare un attributo relativo al nome del conto, impostare la proprietà `Type` dell'attributo su `AccountName`.</span><span class="sxs-lookup"><span data-stu-id="3962f-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="3962f-120">Un attributo del numero di conto, ovvero un attributo usato per la creazione di report.</span><span class="sxs-lookup"><span data-stu-id="3962f-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="3962f-121">Per identificare un attributo relativo al numero di conto, impostare la proprietà `Type` dell'attributo su `AccountNumber`.</span><span class="sxs-lookup"><span data-stu-id="3962f-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="3962f-122">Per altre informazioni sui tipi di attributi, vedere [Configurare tipi di attributi](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="3962f-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="3962f-123">Aggiunta di funzionalità di Business Intelligence per la contabilità tramite la Configurazione guidata funzionalità di Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="3962f-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="3962f-124">Dopo avere definito una dimensione di tipo Conti e avere aggiunto tale dimensione a un cubo, è possibile utilizzare la Configurazione guidata funzionalità di Business Intelligence per aggiungere funzionalità di Business Intelligence per la contabilità, ad esempio funzionalità di identificazione e mapping dei tipi di conto, alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="3962f-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="3962f-125">Per altre informazioni, vedere [Aggiungere funzionalità di Business Intelligence per la contabilità a una dimensione](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="3962f-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3962f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3962f-126">See Also</span></span>  
 <span data-ttu-id="3962f-127">[Attributi e gerarchie di attributi](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="3962f-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="3962f-128">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3962f-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="3962f-129">Tipi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="3962f-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
