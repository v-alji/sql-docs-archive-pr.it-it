---
title: Definire una relazione di tipo fatti e le relative proprietà | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714651"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="6e111-102">Definire una relazione di tipo Fatti e le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="6e111-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="6e111-103">Quando si definisce un nuovo gruppo di misure o una nuova dimensione del cubo, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tenta di rilevare la presenza di una relazione di tipo Fatti per la dimensione e quindi imposta l'utilizzo della dimensione su `Fact`.</span><span class="sxs-lookup"><span data-stu-id="6e111-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="6e111-104">È possibile visualizzare o modificare una relazione di tipo Fatti nella scheda **Utilizzo dimensioni** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="6e111-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="6e111-105">La relazione di tipo Fatti tra una dimensione e un gruppo di misure presenta i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e111-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="6e111-106">Una dimensione del cubo può avere un'unica relazione di tipo Fatti con un particolare gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="6e111-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="6e111-107">Una dimensione del cubo può avere diverse relazioni di tipo Fatti con più gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="6e111-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="6e111-108">L'attributo di granularità per la relazione deve essere l'attributo chiave, ad esempio il numero di transazione, della dimensione.</span><span class="sxs-lookup"><span data-stu-id="6e111-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="6e111-109">Viene così creata una relazione uno-a-uno tra la dimensione e i fatti della tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="6e111-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
