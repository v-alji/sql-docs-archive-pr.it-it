---
title: Applicare le regole di business (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714484"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="70236-102">Applicare le regole business (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="70236-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="70236-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] applicare le regole di business quando si vuole convalidare i dati e confermare che sono validi.</span><span class="sxs-lookup"><span data-stu-id="70236-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="70236-104">È possibile correggere le convalide e pubblicare nuovamente i dati.</span><span class="sxs-lookup"><span data-stu-id="70236-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70236-105">La convalida dei dati si verifica automaticamente quando si pubblicano dati.</span><span class="sxs-lookup"><span data-stu-id="70236-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="70236-106">Per altre informazioni, vedere [Stored procedure di convalida &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="70236-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70236-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="70236-107">Prerequisites</span></span>  
 <span data-ttu-id="70236-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="70236-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="70236-109">È necessario disporre dell'accesso all'area funzionale **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="70236-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="70236-110">È necessario avere un foglio di lavoro attivo che contenga i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="70236-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="70236-111">Per applicare le regole business</span><span class="sxs-lookup"><span data-stu-id="70236-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="70236-112">Nel gruppo **Pubblica e convalida** fare clic su **Applica regole**.</span><span class="sxs-lookup"><span data-stu-id="70236-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70236-113">Il numero di membri (righe) convalidati contemporaneamente dipende da un'impostazione in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70236-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="70236-114">Per altre informazioni, vedere [Impostazioni delle regole business](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="70236-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="70236-115">I dati vengono convalidati automaticamente rispetto alle regole business e vengono visualizzate due colonne.</span><span class="sxs-lookup"><span data-stu-id="70236-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="70236-116">Se queste colonne non sono visualizzate automaticamente, nel gruppo **Pubblica e convalida** fare clic su **Mostra stato** per visualizzarle.</span><span class="sxs-lookup"><span data-stu-id="70236-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70236-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70236-117">See Also</span></span>  
 [<span data-ttu-id="70236-118">Pubblicazione dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="70236-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
