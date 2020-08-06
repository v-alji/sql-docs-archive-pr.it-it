---
title: Advanced Connection Properties | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4edfab68-7e68-45e8-a3f3-a0049ff7eb9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8dc844d1fdfb1e82f0ffa8de93a6a1060ef190cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635194"
---
# <a name="advanced-connection-properties"></a><span data-ttu-id="3feb0-102">Advanced Connection Properties</span><span class="sxs-lookup"><span data-stu-id="3feb0-102">Advanced Connection Properties</span></span>
  <span data-ttu-id="3feb0-103">Utilizzare la finestra di dialogo **Advanced Connection Properties** per aggiungere ulteriori parametri di connessione alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="3feb0-103">Use the **Advanced Connection Properties** dialog box to add more connection parameters to the connection string.</span></span>  
  
 <span data-ttu-id="3feb0-104">Può trattarsi di qualsiasi parametro di connessione ODBC supportato dall'istanza del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="3feb0-104">The additional connection parameters can be any ODBC connection parameter that is supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database instance you are using.</span></span>  
  
 <span data-ttu-id="3feb0-105">I parametri aggiunti utilizzando la finestra di dialogo **Advanced Connection Properties** vengono aggiunti ai parametri selezionati nella finestra di dialogo **Connect to SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="3feb0-105">The parameters added using the **Advanced Connection Properties** dialog box are added to the parameters selected in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="3feb0-106">L'ultima istanza di ogni parametro specificato sostituisce eventuali istanze precedenti del parametro stesso.</span><span class="sxs-lookup"><span data-stu-id="3feb0-106">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="3feb0-107">I parametri aggiunti utilizzando la finestra di dialogo **Advanced Connection Parameters** seguono e sostituiscono i parametri specificati nella finestra di dialogo **SQL Server Connection** .</span><span class="sxs-lookup"><span data-stu-id="3feb0-107">Parameters added using the **Advanced Connection Parameters** dialog box follow and replace the parameters provided in the **SQL Server Connection** dialog box.</span></span> <span data-ttu-id="3feb0-108">Ad esempio, se nella finestra di dialogo **Connessione SQL Server** si specifica SERVER1 come nome del server e la pagina **Parametri aggiuntivi per la connessione** contiene ;SERVER=SERVER2, la connessione viene stabilita con SERVER2.</span><span class="sxs-lookup"><span data-stu-id="3feb0-108">For example, if the **SQL Server Connection** dialog box specifies SERVER1 as the Server name, and the **Additional Connection Parameters** page contains ;SERVER=SERVER2, the connection will be made to SERVER2.</span></span>  
  
 <span data-ttu-id="3feb0-109">I parametri aggiunti utilizzando la finestra di dialogo **Advanced Connection Properties** vengono passati come testo normale.</span><span class="sxs-lookup"><span data-stu-id="3feb0-109">Parameters added using the **Advanced Connection Properties** dialog box are passed as plain text.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3feb0-110">Non includere le credenziali di accesso nella finestra di dialogo **Advanced Connection Properties** ,</span><span class="sxs-lookup"><span data-stu-id="3feb0-110">Do not include login credentials in the **Advanced Connection Properties** dialog box.</span></span> <span data-ttu-id="3feb0-111">non verranno crittografate quando vengono passate in rete.</span><span class="sxs-lookup"><span data-stu-id="3feb0-111">They will not be encrypted when they are passed across the network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3feb0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3feb0-112">See Also</span></span>  
 <span data-ttu-id="3feb0-113">[Accedere a CDC Designer Console](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="3feb0-113">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="3feb0-114">Connessione di SQL Server per la creazione dell'istanza</span><span class="sxs-lookup"><span data-stu-id="3feb0-114">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
