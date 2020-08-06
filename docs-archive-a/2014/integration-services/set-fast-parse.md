---
title: Imposta analisi veloce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623401"
---
# <a name="set-fast-parse"></a><span data-ttu-id="66af6-102">Impostazione dell'analisi veloce</span><span class="sxs-lookup"><span data-stu-id="66af6-102">Set Fast Parse</span></span>
  <span data-ttu-id="66af6-103">È necessario impostare la proprietà relativa all'analisi veloce per ogni colonna dell'origine o della trasformazione in cui questa viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="66af6-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="66af6-104">Per impostare la proprietà, utilizzare l'editor avanzato dell'origine file flat e della trasformazione Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="66af6-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="66af6-105">Per impostare l'analisi veloce</span><span class="sxs-lookup"><span data-stu-id="66af6-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="66af6-106">Fare clic con il pulsante destro del mouse sull'origine file flat o sulla trasformazione Conversione dati e quindi scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="66af6-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="66af6-107">Nella finestra di dialogo **Editor avanzato** fare clic sulla scheda **Proprietà input e output** .</span><span class="sxs-lookup"><span data-stu-id="66af6-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="66af6-108">Nel riquadro **Input e output** fare clic sulla colonna per la quale si desidera abilitare l'analisi veloce.</span><span class="sxs-lookup"><span data-stu-id="66af6-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="66af6-109">Nel Finestra Proprietà espandere il nodo **proprietà personalizzate** , quindi impostare la `FastParse` proprietà su `True` .</span><span class="sxs-lookup"><span data-stu-id="66af6-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="66af6-110">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="66af6-110">Click **OK**.</span></span>  
  
  
