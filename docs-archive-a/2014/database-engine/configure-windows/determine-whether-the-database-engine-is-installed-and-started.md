---
title: Verificare l'installazione e l'avvio del motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, determining if installed
- verifying Database Engine installation
- viewing Database Engine installation
- installed Database Engine verification [SQL Server]
ms.assetid: babb02e4-3521-4b75-b5df-e09205594375
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0a912cf4a89f208543605cc84f480b63955214ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724175"
---
# <a name="determine-whether-the-database-engine-is-installed-and-started"></a><span data-ttu-id="a9e5d-102">Verificare l'installazione e l'avvio del Motore di database</span><span class="sxs-lookup"><span data-stu-id="a9e5d-102">Determine Whether the Database Engine Is Installed and Started</span></span>
  <span data-ttu-id="a9e5d-103">Un'installazione corretta del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installa i file nel file system, crea voci nel Registro di sistema e installa numerosi strumenti.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-103">A successful installation of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installs files to the file system, creates entries in the registry, and installs several tools.</span></span> <span data-ttu-id="a9e5d-104">In questo argomento viene descritto come determinare se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene installato e avviato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9e5d-104">This topic describes how to determine whether the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed and started in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a9e5d-105">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9e5d-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="how-to-view-and-start-the-database-engine-by-using-sql-server-configuration-manager"></a><span data-ttu-id="a9e5d-106">Visualizzazione e avvio di Motore di database utilizzando Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9e5d-106">How to view and start the Database Engine by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="a9e5d-107">Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server**, **Strumenti di configurazione**, quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-107">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
     <span data-ttu-id="a9e5d-108">Se nel menu **Start** non sono presenti gli elementi indicati, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-108">If you do not have these entries on the **Start** menu, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not correctly installed.</span></span> <span data-ttu-id="a9e5d-109">Eseguire il programma di installazione per installare [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9e5d-109">Run Setup to install the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a9e5d-110">Nel riquadro sinistro di **Gestione configurazione SQL Server**fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-110">In **SQL Server Configuration Manager**, on the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="a9e5d-111">Nel riquadro destro sono elencati numerosi servizi correlati a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9e5d-111">The right pane lists several services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a9e5d-112">Se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è installato, il servizio [!INCLUDE[ssDE](../../includes/ssde-md.md)] viene elencato come **SQL Server (MSSQLSERVER)** se si tratta dell'istanza predefinita, oppure come **SQL Server (** \<*instance_name*> **)** , se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è installato come istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-112">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is listed as **SQL Server (MSSQLSERVER)** if it is the default instance; or **SQL Server (**\<*instance_name*>**)**, if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed as a named instance.</span></span> <span data-ttu-id="a9e5d-113">Salvo il caso in cui il nome dell'istanza sia stato modificato, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato come istanza denominata con il nome **SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-113">Unless the instance name is changed, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as a named instance with the name **SQLEXPRESS**.</span></span> <span data-ttu-id="a9e5d-114">Un'icona a forma di triangolo di colore verde indica che [!INCLUDE[ssDE](../../includes/ssde-md.md)] è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-114">A green triangle icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is running.</span></span> <span data-ttu-id="a9e5d-115">Un'icona a forma di quadrato di colore rosso indica che [!INCLUDE[ssDE](../../includes/ssde-md.md)] è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-115">A red square icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is stopped.</span></span>  
  
3.  <span data-ttu-id="a9e5d-116">Per avviare [!INCLUDE[ssDE](../../includes/ssde-md.md)], fare clic con il pulsante destro del mouse su [!INCLUDE[ssDE](../../includes/ssde-md.md)]nel riquadro destro e quindi scegliere **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-116">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)], in the right pane, right-click the [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Start**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9e5d-117">Durante l'installazione, l'utente può selezionare un percorso in cui installare i file di programma e di database.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-117">During setup, the user can select a location in which to install the program files and the database files.</span></span> <span data-ttu-id="a9e5d-118">Se l'utente accetta la posizione predefinita, i file vengono installati in [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] e in C:\Programmi\Microsoft SQL Server\MSSQL.*x*, dove *x* è un numero.</span><span class="sxs-lookup"><span data-stu-id="a9e5d-118">If the user accepts the default location, the files are installed to [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] and C:\Program Files\Microsoft SQL Server\MSSQL.*x*, where *x* is a number.</span></span>  
  
  
