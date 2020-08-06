---
title: Accesso per la navigazione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623363"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="3c5c3-102">Accesso per la navigazione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3c5c3-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="3c5c3-103">L'accesso per la navigazione si applica alla sicurezza dell'oggetto modello, assegnata nella scheda **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="3c5c3-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="3c5c3-104">L'accesso per la navigazione è l'accesso che si ottiene ai livelli superiori a quello per cui è stata assegnata la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="3c5c3-105">In questo esempio le autorizzazioni vengono assegnate a un'entità, pertanto l'accesso per la navigazione viene concesso a livello di modello.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="3c5c3-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="3c5c3-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="3c5c3-107">**Entità**</span><span class="sxs-lookup"><span data-stu-id="3c5c3-107">**Entities**</span></span>  
  
 <span data-ttu-id="3c5c3-108">Quando si assegna un'autorizzazione a un'entità, ai relativi membri foglia o membri consolidati, l'accesso per la navigazione consente di leggere o aggiornare il nome e il codice di tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="3c5c3-109">È inoltre possibile leggere il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="3c5c3-110">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="3c5c3-110">**Attributes**</span></span>  
  
 <span data-ttu-id="3c5c3-111">Quando si assegna un'autorizzazione a un attributo, l'accesso per la navigazione consente di leggere o aggiornare il nome e il codice di tutti i membri nell'entità.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="3c5c3-112">È inoltre possibile leggere il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="3c5c3-113">**raccolte**</span><span class="sxs-lookup"><span data-stu-id="3c5c3-113">**Collections**</span></span>  
  
 <span data-ttu-id="3c5c3-114">Quando si assegnano autorizzazioni alle raccolte, è possibile leggere o aggiornare nome, codice, descrizione e ID proprietario.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="3c5c3-115">È inoltre possibile leggere il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5c3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c5c3-116">See Also</span></span>  
 [<span data-ttu-id="3c5c3-117">Modalità di determinazione delle autorizzazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3c5c3-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
