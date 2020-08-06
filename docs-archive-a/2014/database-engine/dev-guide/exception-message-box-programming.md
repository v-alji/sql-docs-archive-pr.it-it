---
title: Programmazione della finestra di messaggio eccezione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726216"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="0ca49-102">Programmazione della finestra di messaggio eccezione</span><span class="sxs-lookup"><span data-stu-id="0ca49-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="0ca49-103">La finestra di messaggio eccezione è un'interfaccia a livello di codice installata con e utilizzata dai [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componenti grafici di.</span><span class="sxs-lookup"><span data-stu-id="0ca49-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="0ca49-104">La finestra di messaggio eccezione è un assembly gestito supportato che è possibile utilizzare nelle applicazioni per fornire un controllo significativamente maggiore sulla messaggistica e per offrire agli utenti la possibilità di salvare il contenuto dei messaggi di errore per riferimento futuro, nonché per ottenere informazioni sui messaggi.</span><span class="sxs-lookup"><span data-stu-id="0ca49-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="0ca49-105">Poiché la finestra di messaggio eccezione viene installata in tutte le edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di [!INCLUDE[ssEW](../../includes/ssew-md.md)] , è possibile utilizzarla senza alcuna configurazione aggiuntiva in qualsiasi computer in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono stati installati i componenti client.</span><span class="sxs-lookup"><span data-stu-id="0ca49-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="0ca49-106">La classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> dello spazio dei nomi di <xref:Microsoft.SqlServer.MessageBox> presenta, tra le altre, tutte le funzionalità della classe <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0ca49-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="0ca49-107">Ideale per qualsiasi attività per la quale potrebbe essere utilizzata la classe <xref:System.Windows.Forms.MessageBox>, la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> è stata progettata per gestire in modo elegante le eccezioni del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0ca49-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="0ca49-108">La finestra di messaggio eccezione consente di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ca49-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="0ca49-109">Fornire testo per pulsanti personalizzato per un numero massimo di cinque pulsanti.</span><span class="sxs-lookup"><span data-stu-id="0ca49-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="0ca49-110">Le dimensioni dei pulsanti e della finestra di dialogo vengono modificate automaticamente per adeguarsi alla lunghezza del testo.</span><span class="sxs-lookup"><span data-stu-id="0ca49-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="0ca49-111">Consentire agli utenti di copiare facilmente il testo e il titolo del messaggio, il testo del pulsante e gli eventuali collegamenti alla Guida negli Appunti o di inviare queste informazioni in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0ca49-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="0ca49-112">Visualizza tutti gli errori e le eccezioni sottostanti in un albero delle relazioni gerarchiche quando gli utenti fanno clic su **informazioni aggiuntive**.</span><span class="sxs-lookup"><span data-stu-id="0ca49-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="0ca49-113">Consentire agli utenti di decidere se visualizzare nuovamente il messaggio quando si verifica la stessa eccezione.</span><span class="sxs-lookup"><span data-stu-id="0ca49-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="0ca49-114">Accedere a un sistema di Guida online tramite un collegamento alla Guida associato all'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0ca49-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="0ca49-115">Per ulteriori informazioni, vedere la [finestra di messaggio eccezione programma](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="0ca49-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
