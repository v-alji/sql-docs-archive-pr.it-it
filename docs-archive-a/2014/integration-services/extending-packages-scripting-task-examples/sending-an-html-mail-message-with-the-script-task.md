---
title: Invio di un messaggio di posta HTML con l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712180"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="fccd1-102">Invio di un messaggio di posta HTML con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="fccd1-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="fccd1-103">L'attività SendMail di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] supporta solo messaggi di posta in formato di testo normale.</span><span class="sxs-lookup"><span data-stu-id="fccd1-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="fccd1-104">Tuttavia è possibile inviare facilmente messaggi di posta HTML tramite l'attività Script e le funzionalità di posta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fccd1-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="fccd1-105">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="fccd1-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="fccd1-106">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="fccd1-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="fccd1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fccd1-107">Description</span></span>
 <span data-ttu-id="fccd1-108">Nell'esempio seguente viene utilizzato lo spazio dei nomi `System.Net.Mail` per configurare e inviare un messaggio di posta HTML.</span><span class="sxs-lookup"><span data-stu-id="fccd1-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="fccd1-109">Lo script ottiene i campi A, Da, Oggetto e il corpo del messaggio di posta elettronica dalle variabili del pacchetto, li utilizza per creare un nuovo oggetto `MailMessag` e ne imposta la proprietà `IsBodyHtml` su `True`.</span><span class="sxs-lookup"><span data-stu-id="fccd1-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="fccd1-110">Ottiene quindi il nome del server SMTP da un'altra variabile del pacchetto, inizializza un'istanza di `System.Net.Mail.SmtpClient` e chiama il metodo `Send` per inviare il messaggio HTML.</span><span class="sxs-lookup"><span data-stu-id="fccd1-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="fccd1-111">Nell'esempio il messaggio viene incapsulato inviando la funzionalità in una subroutine che potrebbe essere riutilizzata in altri script.</span><span class="sxs-lookup"><span data-stu-id="fccd1-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="fccd1-112">Per configurare questa attività Script di esempio senza una gestione connessione SMTP</span><span class="sxs-lookup"><span data-stu-id="fccd1-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="fccd1-113">Creare le variabili di stringa denominate `HtmlEmailTo`, `HtmlEmailFrom` e `HtmlEmailSubject` e assegnare i valori appropriati per un messaggio di prova valido.</span><span class="sxs-lookup"><span data-stu-id="fccd1-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="fccd1-114">Creare una variabile di stringa denominata `HtmlEmailBody` e assegnarle una stringa di markup HTML.</span><span class="sxs-lookup"><span data-stu-id="fccd1-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="fccd1-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fccd1-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="fccd1-116">Creare una variabile di stringa denominata `HtmlEmailServer` e assegnare il nome di un server SMTP disponibile che accetta messaggi in uscita anonimi.</span><span class="sxs-lookup"><span data-stu-id="fccd1-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="fccd1-117">Assegnare queste cinque variabili alla proprietà **ReadOnlyVariables** di una nuova attività Script.</span><span class="sxs-lookup"><span data-stu-id="fccd1-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="fccd1-118">Importare gli spazi dei nomi `System.Net` e `System.Net.Mail` nel codice.</span><span class="sxs-lookup"><span data-stu-id="fccd1-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="fccd1-119">Il codice di esempio in questo argomento ottiene il nome del server SMTP da una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fccd1-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="fccd1-120">Tuttavia, è possibile sfruttare anche una gestione connessione SMTP per incapsulare le informazioni di connessione ed estrarre il nome del server dalla gestione connessione nel codice.</span><span class="sxs-lookup"><span data-stu-id="fccd1-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="fccd1-121">Il metodo <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> della gestione connessione SMTP restituisce una stringa nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="fccd1-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="fccd1-122">È possibile utilizzare il metodo `String.Split` per separare questo elenco di argomenti in una matrice di stringhe singole in corrispondenza di ogni punto e virgola (;) o segno di uguale (=), quindi estrarre il secondo argomento (pedice 1) dalla matrice come nome del server.</span><span class="sxs-lookup"><span data-stu-id="fccd1-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="fccd1-123">Per configurare questa attività Script di esempio con una gestione connessione SMTP</span><span class="sxs-lookup"><span data-stu-id="fccd1-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="fccd1-124">Modificare l'attività Script configurata precedentemente rimuovendo la variabile `HtmlEmailServer` dall'elenco di **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="fccd1-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="fccd1-125">Sostituire la riga di codice che ottiene il nome del server:</span><span class="sxs-lookup"><span data-stu-id="fccd1-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="fccd1-126">con le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="fccd1-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="fccd1-127">Codice</span><span class="sxs-lookup"><span data-stu-id="fccd1-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="fccd1-128">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fccd1-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fccd1-129">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="fccd1-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fccd1-130">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="fccd1-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fccd1-131">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="fccd1-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="fccd1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fccd1-132">See Also</span></span>
 [<span data-ttu-id="fccd1-133">Attività Invia messaggi</span><span class="sxs-lookup"><span data-stu-id="fccd1-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


