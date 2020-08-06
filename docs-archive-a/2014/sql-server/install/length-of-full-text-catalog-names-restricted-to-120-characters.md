---
title: Lunghezza dei nomi di catalogo full-text limitati a 120 caratteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638242"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="c45bf-102">La lunghezza dei nomi di catalogo full-text è limitata a 120 caratteri</span><span class="sxs-lookup"><span data-stu-id="c45bf-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="c45bf-103">La lunghezza dei nomi di catalogo full-text è limitata a 120 caratteri, rispetto a 128 caratteri nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c45bf-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="c45bf-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c45bf-104">Description</span></span>  
 <span data-ttu-id="c45bf-105">Questa modifica non influisce sui nomi di catalogo esistenti. Tuttavia, gli script che creano cataloghi full-text con nomi più lunghi di 120 caratteri generano un errore.</span><span class="sxs-lookup"><span data-stu-id="c45bf-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="c45bf-106">I nomi del catalogo vengono utilizzati per generare nomi di file logici che corrispondono a cataloghi.</span><span class="sxs-lookup"><span data-stu-id="c45bf-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c45bf-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="c45bf-107">Corrective Action</span></span>  
 <span data-ttu-id="c45bf-108">Modificare tutti gli script che creano cataloghi full-text per assicurarsi che la lunghezza dei nomi di catalogo sia limitata a 120 caratteri.</span><span class="sxs-lookup"><span data-stu-id="c45bf-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45bf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c45bf-109">See Also</span></span>  
 [<span data-ttu-id="c45bf-110">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c45bf-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
