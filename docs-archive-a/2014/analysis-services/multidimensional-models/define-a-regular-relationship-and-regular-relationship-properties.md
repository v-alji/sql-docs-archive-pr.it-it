---
title: Definire una relazione di normale e le proprietà delle relazioni regolari | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b4f49e219a85d5577fb1acddfe14e7afd3b105d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636909"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a><span data-ttu-id="54ed8-102">Definire una relazione di tipo Regolare e le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="54ed8-102">Define a Regular Relationship and Regular Relationship Properties</span></span>
  <span data-ttu-id="54ed8-103">Quando si definisce un nuovo gruppo di misure o una nuova dimensione del cubo, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tenta di rilevare la presenza di una relazione di tipo Regolare e quindi imposta l'utilizzo della dimensione su `Regular`.</span><span class="sxs-lookup"><span data-stu-id="54ed8-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a regular relationship exists and then set the dimension usage setting to `Regular`.</span></span> <span data-ttu-id="54ed8-104">È possibile visualizzare o modificare la relazione di una dimensione regolare nella scheda **Utilizzo dimensioni** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="54ed8-104">You can view or edit a regular dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span>  
  
 <span data-ttu-id="54ed8-105">Quando si definisce la relazione tra una dimensione del cubo e un gruppo di misure, si specifica inoltre l'attributo di granularità per la relazione.</span><span class="sxs-lookup"><span data-stu-id="54ed8-105">When you define the relationship of a cube dimension to a measure group, you also specify the granularity attribute for that relationship.</span></span> <span data-ttu-id="54ed8-106">L'attributo di granularità definisce il livello di dettaglio più basso disponibile nel cubo per la dimensione, che in genere corrisponde all'attributo chiave per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="54ed8-106">The granularity attribute defines the lowest level of detail available in the cube for that dimension, which is generally the key attribute for the dimension.</span></span> <span data-ttu-id="54ed8-107">Talvolta, tuttavia, potrebbe essere necessario impostare diversamente la granularità di una particolare dimensione del cubo in un determinato gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="54ed8-107">However, sometimes you may want to set the granularity of a particular cube dimension in a particular measure group to a different grain.</span></span> <span data-ttu-id="54ed8-108">Potrebbe ad esempio rivelarsi utile impostare l'attributo di granularità per la dimensione Time su Month anziché su Day, se si utilizza un gruppo di misure Sales Quotas o Budget.</span><span class="sxs-lookup"><span data-stu-id="54ed8-108">For example, you may want to set the granularity attribute for the Time dimension to the Month attribute instead of to the Day attribute, if you are using a Sales Quotas or a Budget measure group.</span></span> <span data-ttu-id="54ed8-109">Quando si specifica l'attributo di granularità in base a un attributo diverso dall'attributo chiave, è necessario garantire che tutti gli altri attributi della dimensione siano collegati direttamente o indirettamente a quest'altro attributo tramite relazioni tra attributi.</span><span class="sxs-lookup"><span data-stu-id="54ed8-109">When you specify the granularity attribute to be an attribute other than the key attribute, you must guarantee that all other attributes in the dimension are directly or indirectly linked to this other attribute through attribute relationships.</span></span> <span data-ttu-id="54ed8-110">In caso contrario, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non sarà in grado di eseguire correttamente l'aggregazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="54ed8-110">If not, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will be unable to aggregate data correctly.</span></span>  
  
  
