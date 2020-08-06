---
title: Destinazione di Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724048"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="9a284-102">Destinazione di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="9a284-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="9a284-103">Il componente **Destinazione di Azure Data Lake Store** consente a un pacchetto SSIS di scrivere dati in Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="9a284-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="9a284-104">I formati di file supportati sono testo, Avro e ORC.</span><span class="sxs-lookup"><span data-stu-id="9a284-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="9a284-105">Configurare Destinazione di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="9a284-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="9a284-106">Trascinare **Destinazione di Azure Data Lake Store** nella finestra di progettazione del flusso di dati e fare doppio clic per visualizzare l'editor.</span><span class="sxs-lookup"><span data-stu-id="9a284-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="9a284-107">Nel campo **Gestione connessioni di Azure Data Lake Store** specificare un'istanza esistente di Gestione connessioni di Azure Data Lake Store o creare una nuova istanza che faccia riferimento a un servizio di Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="9a284-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="9a284-108">Per il campo **Percorso file** specificare il nome del file in cui si vogliono scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="9a284-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="9a284-109">Se il file esiste già, il suo contenuto verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="9a284-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="9a284-110">Per il campo **Formato file** specificare il formato file che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="9a284-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="9a284-111">Se il formato del file corrisponde a testo, è necessario impostare il valore **Carattere delimitatore di colonna** .</span><span class="sxs-lookup"><span data-stu-id="9a284-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="9a284-112">Selezionare anche **nomi di colonna nella prima riga di dati** se la prima riga nel file contiene i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="9a284-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="9a284-113">Se il formato del file corrisponde a ORC, è necessario installare JRE per la piattaforma corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9a284-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="9a284-114">Dopo aver specificato le informazioni di connessione, passare alla pagina **Colonne** per eseguire il mapping delle colonne di origine alle colonne di destinazione per il flusso di dati SSIS.</span><span class="sxs-lookup"><span data-stu-id="9a284-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
