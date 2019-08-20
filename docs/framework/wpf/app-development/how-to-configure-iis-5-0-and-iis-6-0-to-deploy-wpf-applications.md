---
title: '方法: WPF アプリケーションを配置するように IIS 5.0 および IIS 6.0 を構成する'
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: 3a9bf79a9d505fef53b62cb589920adcf95ae92a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611507"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="7d3ae-102">方法: WPF アプリケーションを配置するように IIS 5.0 および IIS 6.0 を構成する</span><span class="sxs-lookup"><span data-stu-id="7d3ae-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="7d3ae-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーションは、適切な Multipurpose Internet Mail Extensions (MIME) の種類で構成されていれば、ほとんどの Web サーバーから展開できます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="7d3ae-104">既定では、Microsoft インターネットインフォメーションサービス (IIS) 7.0 はこれらの MIME の種類で構成されていますが、Microsoft インターネットインフォメーションサービス (IIS) 5.0 および Microsoft インターネットインフォメーションサービス (IIS) 6.0 は構成されていません。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="7d3ae-105">このトピックでは、microsoft インターネットインフォメーションサービス (iis) 5.0 と microsoft インターネットインフォメーションサービス (iis) 6.0 を構成し[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]てアプリケーションを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="7d3ae-106">レジストリの*UserAgent*文字列を確認して、システムに .NET Framework がインストールされているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="7d3ae-107">*UserAgent*文字列を調べて .NET Framework がシステムにインストールされているかどうかを確認するスクリプトについては、「 [.NET Framework 3.0 がインストールされているかどうかを検出](how-to-detect-whether-the-net-framework-3-0-is-installed.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="7d3ae-108">コンテンツの有効期限の設定を調整する</span><span class="sxs-lookup"><span data-stu-id="7d3ae-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="7d3ae-109">コンテンツの有効期限の設定を 1 分に調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="7d3ae-110">次の手順では、IIS でこれを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="7d3ae-111">**[スタート]** メニューをクリックして、 **[管理ツール]** をポイントして、 **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="7d3ae-112">コマンド ラインで「SystemRoot%\system32\inetsrv\iis.msc %」と入力して、このアプリケーションを起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="7d3ae-113">**[既定の Web サイト]** ノードが表示されるまで、IIS ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="7d3ae-114">**[Default Web Site]** を右クリックし、コンテキスト メニューの **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="7d3ae-115">**HTTP ヘッダー** タブを選択し、コンテンツの有効期限を有効にする をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="7d3ae-116">1 分後に期限切れになるようにコンテンツを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="7d3ae-117">MIME タイプとファイル拡張子を登録する</span><span class="sxs-lookup"><span data-stu-id="7d3ae-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="7d3ae-118">クライアントのシステムのブラウザーが適切なハンドラーを読み込めるように、いくつかの MIME の種類とファイル拡張子を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="7d3ae-119">次のタイプを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-119">You need to add the following types:</span></span>

|<span data-ttu-id="7d3ae-120">拡張子</span><span class="sxs-lookup"><span data-stu-id="7d3ae-120">Extension</span></span>|<span data-ttu-id="7d3ae-121">[MIME の種類]</span><span class="sxs-lookup"><span data-stu-id="7d3ae-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="7d3ae-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="7d3ae-122">.manifest</span></span>|<span data-ttu-id="7d3ae-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="7d3ae-123">application/manifest</span></span>|
|<span data-ttu-id="7d3ae-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="7d3ae-124">.xaml</span></span>|<span data-ttu-id="7d3ae-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="7d3ae-125">application/xaml+xml</span></span>|
|<span data-ttu-id="7d3ae-126">.application</span><span class="sxs-lookup"><span data-stu-id="7d3ae-126">.application</span></span>|<span data-ttu-id="7d3ae-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="7d3ae-127">application/x-ms-application</span></span>|
|<span data-ttu-id="7d3ae-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="7d3ae-128">.xbap</span></span>|<span data-ttu-id="7d3ae-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="7d3ae-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="7d3ae-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="7d3ae-130">.deploy</span></span>|<span data-ttu-id="7d3ae-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="7d3ae-131">application/octet-stream</span></span>|
|<span data-ttu-id="7d3ae-132">.xps</span><span class="sxs-lookup"><span data-stu-id="7d3ae-132">.xps</span></span>|<span data-ttu-id="7d3ae-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="7d3ae-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="7d3ae-134">クライアントシステムに MIME の種類またはファイル拡張子を登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="7d3ae-135">これらは Microsoft .NET Framework のインストール時に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="7d3ae-136">次の Microsoft Visual Basic Scripting Edition (VBScript) のサンプルでは、必要な MIME の種類が IIS に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="7d3ae-137">スクリプトを使用するには、サーバー上の .vbs ファイルにこのコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="7d3ae-138">その後、コマンド ラインからファイルを実行するか、[!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)] でファイルをダブルクリックして、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> <span data-ttu-id="7d3ae-139">このスクリプトを複数回実行すると、Microsoft インターネットインフォメーションサービス (IIS) 5.0 または Microsoft インターネットインフォメーションサービス (IIS) 6.0 メタベースに複数の MIME マップエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="7d3ae-140">このスクリプトを実行すると、Microsoft インターネットインフォメーションサービス (IIS) 5.0 または Microsoft インターネットインフォメーションサービス (IIS) 6.0 Microsoft 管理コンソール (MMC) で追加された MIME の種類が表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="7d3ae-141">ただし、これらの MIME の種類は、Microsoft インターネットインフォメーションサービス (IIS) 5.0 または Microsoft インターネットインフォメーションサービス (IIS) 6.0 メタベースに追加されています。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="7d3ae-142">次のスクリプトでは、Microsoft インターネットインフォメーションサービス (IIS) 5.0 または Microsoft インターネットインフォメーションサービス (IIS) 6.0 メタベースのすべての MIME の種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

<span data-ttu-id="7d3ae-143">スクリプトを `.vbs` ファイルとして保存し (たとえば、`DiscoverIISMimeTypes.vbs`)、次のコマンドを使用して、コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="7d3ae-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
