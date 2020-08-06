---
title: Associare un attributo a una colonna nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- name columns [Analysis Services]
- attributes [Analysis Services], binding
ms.assetid: 467f0cf3-8691-476d-a7fb-a5df4e374eaf
author: minewiskan
ms.author: owend
ms.openlocfilehash: e25c59d34744e7a067c2b3e83d248c4674772737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636925"
---
# <a name="bind-an-attribute-to-a-name-column"></a><span data-ttu-id="3038c-102">Associare un attributo a una colonna del nome</span><span class="sxs-lookup"><span data-stu-id="3038c-102">Bind an Attribute to a Name Column</span></span>
  <span data-ttu-id="3038c-103">Questa procedura descrive come associare manualmente un attributo al nome di una colonna tramite il riquadro **Attributi** di Progettazione dimensioni e tramite la finestra di dialogo **Associazione oggetto** .</span><span class="sxs-lookup"><span data-stu-id="3038c-103">This procedure describes how to bind an attribute to a name column manually by using the **Attributes** pane in the Dimension Designer and by using the **Object Binding** dialog box.</span></span>  
  
### <a name="to-bind-an-attribute-to-a-name-column"></a><span data-ttu-id="3038c-104">Per associare un attributo a una colonna del nome</span><span class="sxs-lookup"><span data-stu-id="3038c-104">To bind an attribute to a name column</span></span>  
  
1.  <span data-ttu-id="3038c-105">In Progettazione dimensioni aprire la dimensione in cui si desidera creare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="3038c-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="3038c-106">Nel riquadro **Attributi** della scheda **Struttura dimensione** fare clic con il pulsante destro del mouse sull'attributo da configurare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3038c-106">On the **Dimension Structure** tab, in the **Attributes** pane, right-click the attribute that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3038c-107">Nella finestra **Proprietà** individuare la proprietà **NameColumn** e selezionare **(nuovo)**.</span><span class="sxs-lookup"><span data-stu-id="3038c-107">In the **Properties** window, locate the **NameColumn** property, and then select **(new)**.</span></span>  
  
4.  <span data-ttu-id="3038c-108">Nella finestra di dialogo **Associazione oggetto** selezionare **Associazione colonna**per **Tipo di associazione**.</span><span class="sxs-lookup"><span data-stu-id="3038c-108">In the **Object Binding** dialog box, for **Binding type**, select **Column binding**.</span></span>  
  
5.  <span data-ttu-id="3038c-109">Nella casella **Colonna di origine** selezionare la colonna alla quale viene associato l'attributo, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3038c-109">In the **Source column** list, select the column to which the attribute will be bound, and then click **OK**.</span></span>  
  
  
