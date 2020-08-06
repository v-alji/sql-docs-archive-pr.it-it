---
title: Destinazione SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfeb0bfce54c9ebefb5c526656be6b736dc0d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636322"
---
# <a name="sql-server-compact-edition-destination"></a><span data-ttu-id="e9b40-102">Destinazione SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="e9b40-102">SQL Server Compact Edition Destination</span></span>
  <span data-ttu-id="e9b40-103">La destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact consente di scrivere dati in database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="e9b40-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination writes data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact databases.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9b40-104">In un computer a 64 bit è necessario eseguire pacchetti che si connettono a origini dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact in modalità a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="e9b40-104">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="e9b40-105">Il provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact usato in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per la connessione a origini dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact è disponibile solo nella versione a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="e9b40-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
 <span data-ttu-id="e9b40-106">Per configurare la destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, è necessario specificare il nome della tabella in cui la destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact inserisce i dati.</span><span class="sxs-lookup"><span data-stu-id="e9b40-106">You configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination by specifying the name of the table into which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination inserts the data.</span></span> <span data-ttu-id="e9b40-107">Il TableName è contenuto nella proprietà personalizzata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] della destinazione Compact.</span><span class="sxs-lookup"><span data-stu-id="e9b40-107">The custom property TableName of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination contains the table name.</span></span>  
  
 <span data-ttu-id="e9b40-108">Per connettersi a un'origine dati, questa destinazione usa una gestione connessione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact che specifica il provider OLE DB da usare.</span><span class="sxs-lookup"><span data-stu-id="e9b40-108">This destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="e9b40-109">Per altre informazioni, vedere [Configurazione della gestione connessione SQL Server Compact Edition](../connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e9b40-109">For more information, see [SQL Server Compact Edition Connection Manager](../connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e9b40-110">La destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact include la proprietà personalizzata TableName, che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e9b40-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination includes the TableName custom property, which can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="e9b40-111">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Utilizzo delle espressioni di proprietà nei pacchetti](../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate della destinazione SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e9b40-111">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [SQL Server Compact Edition Destination Custom Properties](sql-server-compact-edition-destination-custom-properties.md).</span></span>  
  
 <span data-ttu-id="e9b40-112">La destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact prevede un solo input e non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="e9b40-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination has one input and does not support an error output.</span></span>  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a><span data-ttu-id="e9b40-113">Configurazione della destinazione SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="e9b40-113">Configuration of the SQL Server Compact Edition Destination</span></span>  
 <span data-ttu-id="e9b40-114">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e9b40-114">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e9b40-115">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e9b40-115">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e9b40-116">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9b40-116">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e9b40-117">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="e9b40-117">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e9b40-118">Proprietà personalizzate della destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9b40-118">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e9b40-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e9b40-119">Related Tasks</span></span>  
 <span data-ttu-id="e9b40-120">Per altre informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e9b40-120">For more information about how to set properties of this component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b40-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b40-121">See Also</span></span>  
 [<span data-ttu-id="e9b40-122">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e9b40-122">Data Flow</span></span>](data-flow.md)  
  
  
