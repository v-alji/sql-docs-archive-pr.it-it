---
title: Modificare le proprietà del database Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626843"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="59c85-102">Modificare le proprietà del database Oracle</span><span class="sxs-lookup"><span data-stu-id="59c85-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="59c85-103">Utilizzare la scheda Oracle nell'editor delle proprietà per modificare la descrizione fornita nella pagina Create CDC database della New Instance Wizard e le informazioni di connessione al database di log mining Oracle.</span><span class="sxs-lookup"><span data-stu-id="59c85-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="59c85-104">Di seguito vengono illustrate le informazioni nella scheda **Oracle** .</span><span class="sxs-lookup"><span data-stu-id="59c85-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="59c85-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="59c85-105">**Name**</span></span>  
 <span data-ttu-id="59c85-106">Nome dell'istanza di CDC immesso nella pagina Create CDC Database della New Instance Wizard.</span><span class="sxs-lookup"><span data-stu-id="59c85-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="59c85-107">Questo campo è di sola lettura, pertanto non è possibile modificare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="59c85-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="59c85-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="59c85-108">**Description**</span></span>  
 <span data-ttu-id="59c85-109">È possibile modificare la descrizione della nuova istanza o aggiungerne una se non è stato fatto al momento della creazione dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="59c85-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="59c85-110">**Oracle Connect String**</span><span class="sxs-lookup"><span data-stu-id="59c85-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="59c85-111">Stringa di connessione Oracle al computer contenente il database Oracle in uso.</span><span class="sxs-lookup"><span data-stu-id="59c85-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="59c85-112">Questo campo è di sola lettura, pertanto non è possibile modificare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="59c85-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="59c85-113">In seguito ad alcune modifiche alla stringa di connessione, infatti, l'istanza di Oracle CDC può puntare a un altro database Oracle, danneggiando lo stato dell'istanza archiviato nella tabella **cdc.xdbcdc_config** .</span><span class="sxs-lookup"><span data-stu-id="59c85-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="59c85-114">Qualora fossero necessarie modifiche di piccola entità, è possibile modificare la stringa di connessione direttamente nella tabella di configurazione tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="59c85-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="59c85-115">**Oracle Log Mining Authentication**</span><span class="sxs-lookup"><span data-stu-id="59c85-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="59c85-116">Per immettere le credenziali di autenticazione per il database Oracle che contiene il log miner, selezionare una delle opzioni disponibili in **Authentication**:</span><span class="sxs-lookup"><span data-stu-id="59c85-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="59c85-117">**Windows Authentication**: selezionare questa opzione per utilizzare le credenziali del dominio Windows correnti.</span><span class="sxs-lookup"><span data-stu-id="59c85-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="59c85-118">È possibile utilizzare questa opzione solo se il database Oracle è configurato per l'utilizzo dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="59c85-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="59c85-119">**Oracle Authentication**: se si seleziona questa opzione, è necessario digitare il **nome utente** e la **password** dell'utente nel database Oracle a cui si effettua la connessione.</span><span class="sxs-lookup"><span data-stu-id="59c85-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="59c85-120">È possibile visualizzare le proprietà del database Oracle nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="59c85-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="59c85-121">Quando si utilizza il visualizzatore le informazioni sono in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="59c85-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="59c85-122">Nel visualizzatore è inoltre incluso un elenco delle colonne acquisite nella tabella.</span><span class="sxs-lookup"><span data-stu-id="59c85-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="59c85-123">Per informazioni su come accedere al visualizzatore, vedere [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="59c85-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59c85-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59c85-124">See Also</span></span>  
 <span data-ttu-id="59c85-125">[Modalità di gestione di un servizio CDC da CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="59c85-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="59c85-126">[Connettersi a un database di origine Oracle](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="59c85-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="59c85-127">Connettersi a Oracle</span><span class="sxs-lookup"><span data-stu-id="59c85-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
