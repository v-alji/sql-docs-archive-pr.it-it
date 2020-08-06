---
title: Creare script usando i modelli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717148"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="344da-102">Creare script utilizzando i modelli</span><span class="sxs-lookup"><span data-stu-id="344da-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="344da-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] include numerosi modelli di script contenenti istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] per eseguire le attività più comuni.</span><span class="sxs-lookup"><span data-stu-id="344da-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="344da-104">Tali modelli contengono parametri per i valori specificati dall'utente, ad esempio un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="344da-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="344da-105">L'utilizzo dei parametri consente di digitare il nome una sola volta e quindi copiarlo automaticamente in tutte le posizioni richieste all'interno dello script.</span><span class="sxs-lookup"><span data-stu-id="344da-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="344da-106">È possibile creare modelli personalizzati per supportare gli script che vengono scritti più di frequente.</span><span class="sxs-lookup"><span data-stu-id="344da-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="344da-107">È inoltre possibile riorganizzare l'albero dei modelli spostandoli o creando nuove cartelle dove contenerli.</span><span class="sxs-lookup"><span data-stu-id="344da-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="344da-108">In questa esercitazione verrà utilizzato un modello per creare un database e verranno specificati i parametri del modello.</span><span class="sxs-lookup"><span data-stu-id="344da-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="344da-109">Utilizzo dei modelli</span><span class="sxs-lookup"><span data-stu-id="344da-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="344da-110">Per creare uno script utilizzando un modello</span><span class="sxs-lookup"><span data-stu-id="344da-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="344da-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="344da-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="344da-112">In Esplora modelli i modelli sono organizzati in gruppi.</span><span class="sxs-lookup"><span data-stu-id="344da-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="344da-113">Espandere **Database**e quindi fare doppio clic su **Crea database**.</span><span class="sxs-lookup"><span data-stu-id="344da-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="344da-114">Nella finestra di dialogo **Connetti al motore di database** specificare le informazioni di connessione e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="344da-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="344da-115">Viene visualizzata una nuova finestra dell'editor di query che include il contenuto del modello **Crea database** .</span><span class="sxs-lookup"><span data-stu-id="344da-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="344da-116">Scegliere **Imposta valori per parametri modello** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="344da-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="344da-117">Nella finestra di dialogo **Specifica valori per parametri modello** la colonna **Valore** contiene un valore consigliato per il parametro **Database_Name** .</span><span class="sxs-lookup"><span data-stu-id="344da-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="344da-118">Nella casella del parametro **Nome database** digitare **Marketing**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="344da-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="344da-119">Si noti che il parametro "Marketing" viene inserito in numerosi punti dello script.</span><span class="sxs-lookup"><span data-stu-id="344da-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="344da-120">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="344da-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="344da-121">Creare modelli personalizzati</span><span class="sxs-lookup"><span data-stu-id="344da-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
