---
title: Destinazione BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722932"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="f3374-102">Destinazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="f3374-102">Azure Blob Destination</span></span>
  <span data-ttu-id="f3374-103">Il componente **Destinazione BLOB di Azure** consente a un pacchetto SSIS di scrivere dati in un BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="f3374-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="f3374-104">I formati di file supportati sono CSV e AVRO.</span><span class="sxs-lookup"><span data-stu-id="f3374-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="f3374-105">Trascinare: eliminare la **destinazione BLOB di Azure** nella finestra di progettazione del flusso di dati e fare doppio clic su di essa per visualizzare l'editor.</span><span class="sxs-lookup"><span data-stu-id="f3374-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="f3374-106">Nel campo **Gestione connessione di archiviazione di Azure** specificare un'istanza esistente di Gestione connessioni dell'archiviazione di Azure o creare una nuova istanza che fa riferimento a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="f3374-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="f3374-107">Nel campo **Nome contenitore BLOB** specificare il nome del contenitore BLOB che contiene i file di origine.</span><span class="sxs-lookup"><span data-stu-id="f3374-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="f3374-108">Nel campo **Nome BLOB** specificare il percorso per il BLOB.</span><span class="sxs-lookup"><span data-stu-id="f3374-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="f3374-109">Nel campo **Formato del file BLOB** specificare il formato BLOB che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f3374-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="f3374-110">Se il formato del file è CSV, è necessario impostare il valore **Carattere delimitatore di colonna** .</span><span class="sxs-lookup"><span data-stu-id="f3374-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="f3374-111">Selezionare anche **nomi di colonna nella prima riga di dati** se la prima riga nel file contiene i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="f3374-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="f3374-112">Dopo aver specificato le informazioni di connessione, passare alla pagina **Colonne** per eseguire il mapping delle colonne di origine alle colonne di destinazione per il flusso di dati SSIS.</span><span class="sxs-lookup"><span data-stu-id="f3374-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
