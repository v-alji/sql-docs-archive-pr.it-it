---
title: Usare report personalizzati con proprietà dei nodi di Esplora oggetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: c7b84355-71ba-402d-85af-23826f18b7da
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98701c091dc4729eec487e21102158a30ac369e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711535"
---
# <a name="use-custom-reports-with-object-explorer-node-properties"></a><span data-ttu-id="52808-102">Utilizzo di report personalizzati con proprietà dei nodi di Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="52808-102">Use Custom Reports with Object Explorer Node Properties</span></span>
  <span data-ttu-id="52808-103">I report personalizzati possono essere eseguiti nel contesto di un nodo Esplora oggetti selezionato, a condizione che facciano riferimento ai parametri di report di tale nodo.</span><span class="sxs-lookup"><span data-stu-id="52808-103">Custom reports can execute in the context of a selected Object Explorer node if the custom reports reference the report parameters of that node.</span></span> <span data-ttu-id="52808-104">Un report personalizzato può pertanto utilizzare il contesto corrente, ad esempio il database corrente, oppure un oggetto server o database.</span><span class="sxs-lookup"><span data-stu-id="52808-104">This enables a custom report to use the current context, for example the current database, or a database or server object.</span></span>  
  
  
## <a name="object-explorer-node-report-parameters"></a><span data-ttu-id="52808-105">Parametri di report dei nodi Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="52808-105">Object Explorer Node Report Parameters</span></span>  
  
|<span data-ttu-id="52808-106">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="52808-106">Parameter name</span></span>|<span data-ttu-id="52808-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="52808-107">Data type</span></span>|  
|--------------------|---------------|  
|`ObjectName`|`String`|  
|`ObjectTypeName`|`String`|  
|`Filtered`|`Boolean`|  
|`ServerName`|`String`|  
|`FontName`|`String`|  
|`DatabaseName`|`String`|  
  
## <a name="object-explorer-node-report-parameters-example"></a><span data-ttu-id="52808-108">Esempio relativo ai parametri di report dei nodi Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="52808-108">Object Explorer Node Report Parameters Example</span></span>  
 <span data-ttu-id="52808-109">Per eseguire l'esempio, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="52808-109">To run the example, use the following procedure.</span></span>  
  
 <span data-ttu-id="52808-110">**Per visualizzare i valori dei parametri di report per un nodo Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="52808-110">**To view the report parameter values for a node in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="52808-111">Copiare il codice di esempio seguente in un nuovo file di testo e assegnare al file un nome con estensione rdl.</span><span class="sxs-lookup"><span data-stu-id="52808-111">Copy the following sample code into a new text file and name the file by using an .rdl extension.</span></span>  
  
2.  <span data-ttu-id="52808-112">Copiare il file di report in una cartella creata nel server di database per i report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="52808-112">Copy the report file to a folder that you have created on the database server for custom reports.</span></span>  
  
3.  <span data-ttu-id="52808-113">In fare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] clic con il pulsante destro del mouse su un nodo in Esplora oggetti, scegliere **report**, quindi fare clic su report personalizzati.</span><span class="sxs-lookup"><span data-stu-id="52808-113">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click Custom Reports.</span></span> <span data-ttu-id="52808-114">Nella finestra di dialogo **Apri file** individuare la cartella dei report personalizzati, selezionare il file di report e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="52808-114">In the **Open File** dialog box, locate the custom reports folder and select the report file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="52808-115">Alla prima apertura di un nuovo report personalizzato da un nodo Esplora oggetti, tale report verrà aggiunto all'elenco degli ultimi elementi usati in **Report personalizzati** nel menu di scelta rapida del nodo.</span><span class="sxs-lookup"><span data-stu-id="52808-115">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="52808-116">Analogamente, alla prima apertura, anche un report standard verrà aggiunto all'elenco degli ultimi elementi usati in **Report personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="52808-116">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="52808-117">Se viene eliminato un file di un report personalizzato, alla successiva selezione dell'elemento verrà visualizzato un messaggio che chiederà di eliminare la relativa voce dall'elenco degli ultimi elementi utilizzati.</span><span class="sxs-lookup"><span data-stu-id="52808-117">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="52808-118">Per modificare il numero dei file visualizzati nell'elenco degli ultimi elementi usati, scegliere **Opzioni** dal menu **Strumenti**, espandere la cartella **Ambiente** e quindi fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="52808-118">To change the number of files displayed on the recently used list, on the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="52808-119">Modificare il numero in **Display files in recently used list**(Visualizza file nell'elenco degli ultimi file usati).</span><span class="sxs-lookup"><span data-stu-id="52808-119">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="custom-report-code-sample"></a><span data-ttu-id="52808-120">Esempio di codice per un report personalizzato</span><span class="sxs-lookup"><span data-stu-id="52808-120">Custom Report Code Sample</span></span>  
 <span data-ttu-id="52808-121">Il report creato mediante il codice seguente utilizzerà i parametri associati a un nodo Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="52808-121">The report that is created by using the following code will use the parameters that are associated with an Object Explorer node.</span></span>  
  
 `<?xml version="1.0" encoding="utf-8"?>`  
  
 `<Report xmlns="https://schemas.microsoft.com/sqlserver/reporting/2005/01/reportdefinition" xmlns:rd="https://schemas.microsoft.com/SQLServer/reporting/reportdesigner">`  
  
 `<ReportParameters>`  
  
 `<ReportParameter Name="ObjectName">`  
  
 `<DataType>String</DataType>`  
  
 `<Nullable>true</Nullable>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>ObjectName</Prompt>`  
  
 `</ReportParameter>`  
  
 `<ReportParameter Name="ObjectTypeName">`  
  
 `<DataType>String</DataType>`  
  
 `<Nullable>true</Nullable>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>ObjectTypeName</Prompt>`  
  
 `</ReportParameter>`  
  
 `<ReportParameter Name="Filtered">`  
  
 `<DataType>Boolean</DataType>`  
  
 `<Nullable>true</Nullable>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>Filtered</Prompt>`  
  
 `</ReportParameter>`  
  
 `<ReportParameter Name="ServerName">`  
  
 `<DataType>String</DataType>`  
  
 `<Nullable>true</Nullable>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>ServerName</Prompt>`  
  
 `</ReportParameter>`  
  
 `<ReportParameter Name="FontName">`  
  
 `<DataType>String</DataType>`  
  
 `<DefaultValue>`  
  
 `<Values>`  
  
 `<Value>Tahoma</Value>`  
  
 `</Values>`  
  
 `</DefaultValue>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>FontName</Prompt>`  
  
 `</ReportParameter>`  
  
 `<ReportParameter Name="DatabaseName">`  
  
 `<DataType>String</DataType>`  
  
 `<Nullable>true</Nullable>`  
  
 `<DefaultValue>`  
  
 `<Values>`  
  
 `<Value>master</Value>`  
  
 `</Values>`  
  
 `</DefaultValue>`  
  
 `<AllowBlank>true</AllowBlank>`  
  
 `<Prompt>DatabaseName</Prompt>`  
  
 `</ReportParameter>`  
  
 `</ReportParameters>`  
  
 `<DataSources>`  
  
 `<DataSource Name="AllReportParameters">`  
  
 `<ConnectionProperties>`  
  
 `<IntegratedSecurity>true</IntegratedSecurity>`  
  
 `<ConnectString>Data Source=.</ConnectString>`  
  
 `<DataProvider>SQL</DataProvider>`  
  
 `</ConnectionProperties>`  
  
 `<rd:DataSourceID>f1feee4c-0fdc-4301-9efa-3cd89eed2d9f</rd:DataSourceID>`  
  
 `</DataSource>`  
  
 `</DataSources>`  
  
 `<BottomMargin>1in</BottomMargin>`  
  
 `<RightMargin>1in</RightMargin>`  
  
 `<rd:DrawGrid>true</rd:DrawGrid>`  
  
 `<InteractiveWidth>8.5in</InteractiveWidth>`  
  
 `<rd:SnapToGrid>true</rd:SnapToGrid>`  
  
 `<Body>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox1">`  
  
 `<rd:DefaultName>textbox1</rd:DefaultName>`  
  
 `<ZIndex>1</ZIndex>`  
  
 `<Width>6in</Width>`  
  
 `<Style>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>20pt</FontSize>`  
  
 `<Color>SteelBlue</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Height>0.36in</Height>`  
  
 `<Value>AllReportParameters</Value>`  
  
 `</Textbox>`  
  
 `<Table Name="table1">`  
  
 `<DataSetName>AllReportParameters</DataSetName>`  
  
 `<Top>0.36in</Top>`  
  
 `<Details>`  
  
 `<TableRows>`  
  
 `<TableRow>`  
  
 `<TableCells>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="ObjectName">`  
  
 `<rd:DefaultName>ObjectName</rd:DefaultName>`  
  
 `<ZIndex>5</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!ObjectName.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="ObjectTypeName">`  
  
 `<rd:DefaultName>ObjectTypeName</rd:DefaultName>`  
  
 `<ZIndex>4</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!ObjectTypeName.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="Filtered">`  
  
 `<rd:DefaultName>Filtered</rd:DefaultName>`  
  
 `<ZIndex>3</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!Filtered.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="ServerName">`  
  
 `<rd:DefaultName>ServerName</rd:DefaultName>`  
  
 `<ZIndex>2</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!ServerName.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="FontName">`  
  
 `<rd:DefaultName>FontName</rd:DefaultName>`  
  
 `<ZIndex>1</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!FontName.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="DatabaseName">`  
  
 `<rd:DefaultName>DatabaseName</rd:DefaultName>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>=Parameters!DatabaseName.Value</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `</TableCells>`  
  
 `<Height>0.21in</Height>`  
  
 `</TableRow>`  
  
 `</TableRows>`  
  
 `</Details>`  
  
 `<Header>`  
  
 `<TableRows>`  
  
 `<TableRow>`  
  
 `<TableCells>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox2">`  
  
 `<rd:DefaultName>textbox2</rd:DefaultName>`  
  
 `<ZIndex>11</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>ObjectName</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox3">`  
  
 `<rd:DefaultName>textbox3</rd:DefaultName>`  
  
 `<ZIndex>10</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>ObjectTypeName</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox4">`  
  
 `<rd:DefaultName>textbox4</rd:DefaultName>`  
  
 `<ZIndex>9</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>Filtered</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox5">`  
  
 `<rd:DefaultName>textbox5</rd:DefaultName>`  
  
 `<ZIndex>8</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>ServerName</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox6">`  
  
 `<rd:DefaultName>textbox6</rd:DefaultName>`  
  
 `<ZIndex>7</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>FontName</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `<TableCell>`  
  
 `<ReportItems>`  
  
 `<Textbox Name="textbox7">`  
  
 `<rd:DefaultName>textbox7</rd:DefaultName>`  
  
 `<ZIndex>6</ZIndex>`  
  
 `<Style>`  
  
 `<BorderStyle>`  
  
 `<Default>Solid</Default>`  
  
 `</BorderStyle>`  
  
 `<PaddingLeft>2pt</PaddingLeft>`  
  
 `<PaddingBottom>2pt</PaddingBottom>`  
  
 `<FontFamily>Tahoma</FontFamily>`  
  
 `<FontWeight>700</FontWeight>`  
  
 `<FontSize>11pt</FontSize>`  
  
 `<BorderColor>`  
  
 `<Default>LightGrey</Default>`  
  
 `</BorderColor>`  
  
 `<BackgroundColor>SteelBlue</BackgroundColor>`  
  
 `<Color>White</Color>`  
  
 `<PaddingRight>2pt</PaddingRight>`  
  
 `<PaddingTop>2pt</PaddingTop>`  
  
 `</Style>`  
  
 `<CanGrow>true</CanGrow>`  
  
 `<Value>DatabaseName</Value>`  
  
 `</Textbox>`  
  
 `</ReportItems>`  
  
 `</TableCell>`  
  
 `</TableCells>`  
  
 `<Height>0.22in</Height>`  
  
 `</TableRow>`  
  
 `</TableRows>`  
  
 `<RepeatOnNewPage>true</RepeatOnNewPage>`  
  
 `</Header>`  
  
 `<TableColumns>`  
  
 `<TableColumn>`  
  
 `<Width>3in</Width>`  
  
 `</TableColumn>`  
  
 `<TableColumn>`  
  
 `<Width>1.5in</Width>`  
  
 `</TableColumn>`  
  
 `<TableColumn>`  
  
 `<Width>0.75in</Width>`  
  
 `</TableColumn>`  
  
 `<TableColumn>`  
  
 `<Width>1.125in</Width>`  
  
 `</TableColumn>`  
  
 `<TableColumn>`  
  
 `<Width>2in</Width>`  
  
 `</TableColumn>`  
  
 `<TableColumn>`  
  
 `<Width>1.375in</Width>`  
  
 `</TableColumn>`  
  
 `</TableColumns>`  
  
 `</Table>`  
  
 `</ReportItems>`  
  
 `<Height>0.79in</Height>`  
  
 `</Body>`  
  
 `<rd:ReportID>abb14e58-fd36-495a-89ff-b66f29ef287b</rd:ReportID>`  
  
 `<LeftMargin>1in</LeftMargin>`  
  
 `<DataSets>`  
  
 `<DataSet Name="AllReportParameters">`  
  
 `<Query>`  
  
 `<rd:UseGenericDesigner>true</rd:UseGenericDesigner>`  
  
 `<CommandText>SELECT 1`  
  
 `</CommandText>`  
  
 `<DataSourceName>AllReportParameters</DataSourceName>`  
  
 `</Query>`  
  
 `<Fields>`  
  
 `<Field Name="ObjectName">`  
  
 `<rd:TypeName>System.String</rd:TypeName>`  
  
 `<DataField>ObjectName</DataField>`  
  
 `</Field>`  
  
 `<Field Name="ObjectTypeName">`  
  
 `<rd:TypeName>System.String</rd:TypeName>`  
  
 `<DataField>ObjectTypeName</DataField>`  
  
 `</Field>`  
  
 `<Field Name="Filtered">`  
  
 `<rd:TypeName>System.Boolean</rd:TypeName>`  
  
 `<DataField>Filtered</DataField>`  
  
 `</Field>`  
  
 `<Field Name="ServerName">`  
  
 `<rd:TypeName>System.String</rd:TypeName>`  
  
 `<DataField>ServerName</DataField>`  
  
 `</Field>`  
  
 `<Field Name="FontName">`  
  
 `<rd:TypeName>System.String</rd:TypeName>`  
  
 `<DataField>FontName</DataField>`  
  
 `</Field>`  
  
 `<Field Name="DatabaseName">`  
  
 `<rd:TypeName>System.String</rd:TypeName>`  
  
 `<DataField>DatabaseName</DataField>`  
  
 `</Field>`  
  
 `</Fields>`  
  
 `</DataSet>`  
  
 `</DataSets>`  
  
 `<Width>6.875in</Width>`  
  
 `<InteractiveHeight>11in</InteractiveHeight>`  
  
 `<Language>en-US</Language>`  
  
 `<TopMargin>1in</TopMargin>`  
  
 `</Report>`  
  
## <a name="see-also"></a><span data-ttu-id="52808-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52808-122">See Also</span></span>  
 <span data-ttu-id="52808-123">[Report personalizzati in Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="52808-123">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="52808-124">[Aggiungere un report personalizzato a Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="52808-124">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="52808-125">Visualizzazione di avvisi relativi all'esecuzione di report personalizzati</span><span class="sxs-lookup"><span data-stu-id="52808-125">Unsuppress Run Custom Report Warnings</span></span>](unsuppress-run-custom-report-warnings.md)  
  
  
