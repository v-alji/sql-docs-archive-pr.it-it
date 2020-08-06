---
title: Gestione connessione Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712331"
---
# <a name="azure-hdinsight-connection-manager"></a><span data-ttu-id="097db-102">Gestione connessione Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="097db-102">Azure HDInsight Connection Manager</span></span>
<span data-ttu-id="097db-103">La **gestione connessione Azure HDInsight** consente a un pacchetto SSIS di connettersi a un cluster HDInsight di Azure.</span><span class="sxs-lookup"><span data-stu-id="097db-103">The **Azure HDInsight Connection Manager** enables an SSIS package to connect to an Azure HDInsight cluster.</span></span>

<span data-ttu-id="097db-104">Per creare e configurare una **gestione connessione Azure HDInsight**, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="097db-104">To create and configure an **Azure HDInsight Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="097db-105">Nella finestra di dialogo **Aggiungi gestione connessione SSIS** selezionare **AzureHDInsight**e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="097db-105">In the **Add SSIS Connection Manager** dialog box, select **AzureHDInsight**, and click **Add**.</span></span>
2. <span data-ttu-id="097db-106">Nella finestra di dialogo **Editor gestione connessione Azure HDInsight** specificare il **nome DNS del cluster** (senza il prefisso del protocollo), il **nome utente** e la **password** del cluster HDInsight a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="097db-106">In the **Azure HDInsight Connection Manager Editor** dialog box, specify the **Cluster DNS name** (without the protocol prefix), **Username**, and **Password** for the HDInsight cluster to connect to.</span></span>
3. <span data-ttu-id="097db-107">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="097db-107">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="097db-108">È possibile visualizzare le proprietà del componente Gestione connessione create nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="097db-108">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
