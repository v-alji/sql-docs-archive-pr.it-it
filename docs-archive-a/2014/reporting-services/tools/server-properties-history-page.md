---
title: Proprietà server (pagina Cronologia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629716"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="268fd-102">Proprietà server (pagina Cronologia)</span><span class="sxs-lookup"><span data-stu-id="268fd-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="268fd-103">Utilizzare questa pagina per impostare un valore predefinito relativo al numero di copie di cronologia dei report da mantenere.</span><span class="sxs-lookup"><span data-stu-id="268fd-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="268fd-104">Il valore predefinito rappresenta un'impostazione iniziale che definisce i limiti della cronologia di tutti i report.</span><span class="sxs-lookup"><span data-stu-id="268fd-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="268fd-105">È possibile modificare queste impostazioni per singoli report.</span><span class="sxs-lookup"><span data-stu-id="268fd-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="268fd-106">La cronologia del report è una raccolta di snapshot del report che includono layout e dati del report al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="268fd-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="268fd-107">È possibile utilizzare la cronologia del report per conservare una copia di un report in una data o un'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="268fd-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="268fd-108">È possibile creare e gestire la cronologia del report per singoli report in esecuzione in un server di report in modalità nativa o in un server di report configurato per la modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268fd-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="268fd-109">Gli snapshot della cronologia del report vengono archiviati nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="268fd-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="268fd-110">Se si conserva un numero illimitato di snapshot, controllare periodicamente la dimensione del database per verificare che non stia aumentando troppo velocemente o che non occupi troppo spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="268fd-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="268fd-111">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un'istanza del server di report, fare clic con il pulsante destro del mouse sul nome del server di report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="268fd-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="268fd-112">Fare clic su **Cronologia** per aprire la pagina.</span><span class="sxs-lookup"><span data-stu-id="268fd-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="268fd-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="268fd-113">Options</span></span>  
 <span data-ttu-id="268fd-114">**Nessun limite per il numero di snapshot archiviabili nella cronologia**</span><span class="sxs-lookup"><span data-stu-id="268fd-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="268fd-115">Consente di conservare tutti gli snapshot della cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="268fd-115">Retain all report history snapshots.</span></span> <span data-ttu-id="268fd-116">Per mantenere ridotte le dimensioni della cronologia del report sarà necessario eliminare manualmente gli snapshot non più necessari.</span><span class="sxs-lookup"><span data-stu-id="268fd-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="268fd-117">**Numero massimo di copie della cronologia**</span><span class="sxs-lookup"><span data-stu-id="268fd-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="268fd-118">Consente di conservare un numero fisso di snapshot della cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="268fd-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="268fd-119">Raggiunto tale limite, le copie meno recenti vengono rimosse dalla cronologia del report per fare spazio alle copie più recenti.</span><span class="sxs-lookup"><span data-stu-id="268fd-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="268fd-120">Se si imposta tale limite in un momento successivo e il limite viene superato, la cronologia dei report nel server viene ridotta di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="268fd-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="268fd-121">Vengono eliminati per primi gli snapshot del report meno recenti.</span><span class="sxs-lookup"><span data-stu-id="268fd-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="268fd-122">Se la cronologia è vuota o include un numero di snapshot inferiore al limite, vengono aggiunti nuovi snapshot del report.</span><span class="sxs-lookup"><span data-stu-id="268fd-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="268fd-123">Quando viene raggiunto il limite, all'aggiunta di un nuovo snapshot del report viene eliminato lo snapshot meno recente.</span><span class="sxs-lookup"><span data-stu-id="268fd-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="268fd-124">See Also</span></span>  
 <span data-ttu-id="268fd-125">[Impostazione delle proprietà del server di report &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="268fd-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="268fd-126">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="268fd-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="268fd-127">Guida sensibile al contesto del server di report in Management Studio</span><span class="sxs-lookup"><span data-stu-id="268fd-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
