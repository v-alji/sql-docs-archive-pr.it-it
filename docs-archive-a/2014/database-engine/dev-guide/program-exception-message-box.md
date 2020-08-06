---
title: Finestra di messaggio eccezione programma | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724911"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="1de9f-102">Programmare la finestra di messaggio eccezione</span><span class="sxs-lookup"><span data-stu-id="1de9f-102">Program Exception Message Box</span></span>
  <span data-ttu-id="1de9f-103">È possibile usare la finestra di messaggio eccezione nelle applicazioni per offrire un controllo maggiore sull'invio e la ricezione di messaggi rispetto a quello garantito dalla classe <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="1de9f-104">Per ulteriori informazioni, vedere la pagina relativa alla [programmazione della finestra di messaggio eccezione](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="1de9f-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="1de9f-105">Per informazioni su come ottenere e distribuire il file dll della finestra di messaggio eccezione, vedere [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="1de9f-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="1de9f-106">Procedura</span><span class="sxs-lookup"><span data-stu-id="1de9f-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="1de9f-107">Per gestire un'eccezione tramite la finestra di messaggio eccezione</span><span class="sxs-lookup"><span data-stu-id="1de9f-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="1de9f-108">Aggiungere un riferimento all'assembly Microsoft.ExceptionMessageBox.dll nel progetto di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1de9f-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="1de9f-109">Opzionale Aggiungere una `using` direttiva (C#) o `Imports` ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) per usare lo <xref:Microsoft.SqlServer.MessageBox> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1de9f-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="1de9f-110">Creare un blocco Try-Catch per gestire l'eccezione anticipata.</span><span class="sxs-lookup"><span data-stu-id="1de9f-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="1de9f-111">All'interno del blocco `catch` creare un'istanza della classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="1de9f-112">Passare l' <xref:System.Exception> oggetto gestito dal `try` - `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="1de9f-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="1de9f-113">(Facoltativo) Impostare una o più delle proprietà seguenti su <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="1de9f-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="1de9f-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumerazione che specifica i pulsanti da visualizzare nella finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Enumerazione che specifica il pulsante predefinito per la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumerazione utilizzata per controllare altri comportamenti della finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumerazione che specifica il simbolo da visualizzare nella finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="1de9f-118">Chiamare il metodo <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="1de9f-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="1de9f-119">Passare la finestra padre alla quale appartiene la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="1de9f-120">(Facoltativo) Annotare il valore dell'enumerazione <xref:System.Windows.Forms.DialogResult> restituita se è necessario determinare su quale pulsante l'utente ha fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1de9f-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="1de9f-121">Per visualizzare la finestra di messaggio eccezione senza un'eccezione</span><span class="sxs-lookup"><span data-stu-id="1de9f-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="1de9f-122">Aggiungere un riferimento all'assembly Microsoft.ExceptionMessageBox.dll nel progetto di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1de9f-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="1de9f-123">Opzionale Aggiungere una `using` direttiva (C#) o `Imports` (Visual Basic .NET) per usare lo <xref:Microsoft.SqlServer.MessageBox> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1de9f-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="1de9f-124">Creare un'istanza della classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="1de9f-125">Passare il testo del messaggio come valore <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="1de9f-126">(Facoltativo) Impostare una o più delle proprietà seguenti su <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="1de9f-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="1de9f-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumerazione che specifica i pulsanti da visualizzare nella finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A>: didascalia della finestra di dialogo della finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Enumerazione che specifica il pulsante predefinito per la finestra di dialogo della finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumerazione utilizzata per controllare altri comportamenti della finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="1de9f-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumerazione che specifica il simbolo da visualizzare nella finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="1de9f-132">Chiamare il metodo <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="1de9f-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="1de9f-133">Passare la finestra padre alla quale appartiene la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="1de9f-134">(Facoltativo) Annotare il valore dell'enumerazione <xref:System.Windows.Forms.DialogResult> restituita se è necessario determinare su quale pulsante l'utente ha fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1de9f-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="1de9f-135">Per visualizzare la finestra di messaggio eccezione con pulsanti personalizzati</span><span class="sxs-lookup"><span data-stu-id="1de9f-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="1de9f-136">Aggiungere un riferimento all'assembly Microsoft.ExceptionMessageBox.dll nel progetto di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1de9f-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="1de9f-137">Opzionale Aggiungere una `using` direttiva (C#) o `Imports` (Visual Basic .NET) per usare lo <xref:Microsoft.SqlServer.MessageBox> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1de9f-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="1de9f-138">Creare un'istanza della classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de9f-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="1de9f-139">Passare l' <xref:System.Exception> oggetto gestito da un `try` - `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="1de9f-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="1de9f-140">Passare il testo del messaggio come valore <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="1de9f-141">Impostare uno dei seguenti valori per <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span><span class="sxs-lookup"><span data-stu-id="1de9f-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="1de9f-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>-Visualizza i pulsanti **Interrompi**, **Riprova**e **Ignora** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="1de9f-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom>: visualizza pulsanti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1de9f-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="1de9f-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>-Visualizza il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="1de9f-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>: Visualizza i pulsanti **OK** e **Annulla** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="1de9f-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>: Visualizza i pulsanti **Riprova** e **Annulla** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="1de9f-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>: Visualizza i pulsanti **Sì** e **No** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="1de9f-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>: Visualizza i pulsanti **Sì**, **No**e **Annulla** .</span><span class="sxs-lookup"><span data-stu-id="1de9f-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="1de9f-149">(Facoltativo) Se si usano pulsanti personalizzati, chiamare uno degli overload del metodo <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> per specificare il testo per un massimo di cinque pulsanti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1de9f-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="1de9f-150">Chiamare il metodo <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="1de9f-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="1de9f-151">Passare la finestra padre alla quale appartiene la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="1de9f-152">(Facoltativo) Annotare il valore dell'enumerazione <xref:System.Windows.Forms.DialogResult> restituita se è necessario determinare su quale pulsante l'utente ha fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1de9f-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="1de9f-153">Se si usano pulsanti personalizzati, annotare il valore di <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> per la proprietà <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> per determinare su quale pulsante personalizzato l'utente ha fatto clic.</span><span class="sxs-lookup"><span data-stu-id="1de9f-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="1de9f-154">Per consentire agli utenti di decidere se visualizzare la finestra di messaggio eccezione</span><span class="sxs-lookup"><span data-stu-id="1de9f-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="1de9f-155">Aggiungere un riferimento all'assembly Microsoft.ExceptionMessageBox.dll nel progetto di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1de9f-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="1de9f-156">Opzionale Aggiungere una `using` direttiva (C#) o `Imports` (Visual Basic .NET) per usare lo <xref:Microsoft.SqlServer.MessageBox> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1de9f-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="1de9f-157">Creare un'istanza della classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de9f-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="1de9f-158">Passare l' <xref:System.Exception> oggetto gestito da un `try` - `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="1de9f-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="1de9f-159">Passare il testo del messaggio come valore <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="1de9f-160">Impostare la proprietà <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="1de9f-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="1de9f-161">(Facoltativo) Specificare il testo per chiedere all'utente di decidere se visualizzare nuovamente la finestra di messaggio eccezione per <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span><span class="sxs-lookup"><span data-stu-id="1de9f-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="1de9f-162">Il testo predefinito è "Non visualizzare più questo messaggio".</span><span class="sxs-lookup"><span data-stu-id="1de9f-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="1de9f-163">Se è necessario mantenere la decisione dell'utente solo per la durata dell'esecuzione dell'applicazione, impostare il valore di <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> su una variabile <xref:System.Boolean> globale.</span><span class="sxs-lookup"><span data-stu-id="1de9f-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="1de9f-164">Valutare questo valore prima di creare un'istanza della finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="1de9f-165">Se è necessario archiviare in modo permanente la decisione di un utente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de9f-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="1de9f-166">Chiamare il metodo CreateSubKey per aprire una chiave del Registro di sistema personalizzata usata dall'applicazione e impostare <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> sull'oggetto RegistryKey restituito.</span><span class="sxs-lookup"><span data-stu-id="1de9f-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="1de9f-167">Impostare <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> sul nome del valore del Registro di sistema usato.</span><span class="sxs-lookup"><span data-stu-id="1de9f-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="1de9f-168">Impostare <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="1de9f-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="1de9f-169">Chiamare il metodo <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="1de9f-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="1de9f-170">La chiave del Registro di sistema specificata viene valutata e la finestra di messaggio eccezione viene visualizzata solo se i dati archiviati in tale chiave sono pari a 0.</span><span class="sxs-lookup"><span data-stu-id="1de9f-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="1de9f-171">Se la finestra di dialogo viene visualizzata e l'utente seleziona la casella di controllo prima di fare clic su un pulsante, i dati nella chiave del Registro di sistema vengono impostati su 1.</span><span class="sxs-lookup"><span data-stu-id="1de9f-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de9f-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-172">Example</span></span>  
 <span data-ttu-id="1de9f-173">In questo esempio viene usata la finestra di messaggio eccezione con il pulsante **OK** per visualizzare le informazioni di un'eccezione dell'applicazione che include l'eccezione gestita insieme ad altre informazioni specifiche dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="1de9f-174">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-174">Example</span></span>  
 <span data-ttu-id="1de9f-175">In questo esempio viene usata la finestra di messaggio eccezione con i pulsanti **Sì** e **No** da cui l'utente sceglie.</span><span class="sxs-lookup"><span data-stu-id="1de9f-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="1de9f-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-176">Example</span></span>  
 <span data-ttu-id="1de9f-177">In questo esempio viene usata la finestra di messaggio eccezione con pulsanti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1de9f-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="1de9f-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-178">Example</span></span>  
 <span data-ttu-id="1de9f-179">In questo esempio viene usata la casella di controllo per determinare se visualizzare la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="1de9f-180">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-180">Example</span></span>  
 <span data-ttu-id="1de9f-181">In questo esempio vengono usate la casella di controllo e una chiave del Registro di sistema per determinare se visualizzare la finestra di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="1de9f-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="1de9f-182">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9f-182">Example</span></span>  
 <span data-ttu-id="1de9f-183">In questo esempio viene usata la finestra di messaggio eccezione per visualizzare informazioni aggiuntive utili per la risoluzione dei problemi o il debug.</span><span class="sxs-lookup"><span data-stu-id="1de9f-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
