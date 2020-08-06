---
title: 'Passaggio 3: Modifica della gestione connessione file flat | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624820"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="9e71e-102">Passaggio 3: Modifica della gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="9e71e-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="9e71e-103">In questa attività verrà modificata la gestione connessione file flat creata e configurata nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="9e71e-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="9e71e-104">Al momento della creazione, la gestione connessione file flat era stata configurata per caricare staticamente un singolo file.</span><span class="sxs-lookup"><span data-stu-id="9e71e-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="9e71e-105">Per abilitare Gestione connessione file flat affinché carichi i file in modo iterativo, è necessario modificare la proprietà ConnectionString della gestione connessione in modo che accetti la variabile `User:varFileName`definita dall'utente contenente il percorso del file da caricare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9e71e-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="9e71e-106">La modifica della gestione connessione in modo da usare il valore della variabile `User::varFileName`definita dall'utente per popolare la proprietà ConnectionString consente alla gestione connessione di connettersi a file flat diversi.</span><span class="sxs-lookup"><span data-stu-id="9e71e-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="9e71e-107">In fase di esecuzione, ogni iterazione del contenitore Ciclo Foreach determina l'aggiornamento dinamico della variabile `User::varFileName` .</span><span class="sxs-lookup"><span data-stu-id="9e71e-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="9e71e-108">L'aggiornamento della variabile quindi consente alla gestione connessione di connettersi a un file flat diverso e all'attività Flusso di dati di elaborare un set di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="9e71e-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="9e71e-109">Per configurare la gestione connessione file flat in modo da utilizzare una variabile per la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="9e71e-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="9e71e-110">Nel riquadro **Gestioni connessioni** fare clic con il pulsante destro del mouse su **Sample Flat File Source Data**e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9e71e-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9e71e-111">Nel Finestra Proprietà, per le **espressioni**, fare clic nella cella vuota, quindi fare clic sul pulsante con i puntini di sospensione **(...)**.</span><span class="sxs-lookup"><span data-stu-id="9e71e-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="9e71e-112">Nella finestra di dialogo **Editor espressioni di proprietà** Digitare o selezionare nella colonna **Proprietà** `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="9e71e-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="9e71e-113">Nella colonna **espressione** fare clic sul pulsante con i puntini di sospensione **(...)** per aprire la finestra di dialogo **Generatore di espressioni** .</span><span class="sxs-lookup"><span data-stu-id="9e71e-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="9e71e-114">Nella finestra di dialogo **Generatore di espressioni** espandere il nodo **Variabili** .</span><span class="sxs-lookup"><span data-stu-id="9e71e-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="9e71e-115">Trascinare la variabile **User:: varFileName**nella casella **espressione** .</span><span class="sxs-lookup"><span data-stu-id="9e71e-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="9e71e-116">Fare clic su **OK** per chiudere la finestra di dialogo **Generatore di espressioni** .</span><span class="sxs-lookup"><span data-stu-id="9e71e-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="9e71e-117">Fare nuovamente clic su **OK** per chiudere la finestra di dialogo **Editor espressioni di proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9e71e-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="9e71e-118">Attività della lezione successiva</span><span class="sxs-lookup"><span data-stu-id="9e71e-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="9e71e-119">Passaggio 4: Test del pacchetto creato nella lezione 2 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="9e71e-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
