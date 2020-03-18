---
title: CorFlags.exe (CorFlags 変換ツール)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129861"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="34dce-102">CorFlags.exe (CorFlags 変換ツール)</span><span class="sxs-lookup"><span data-stu-id="34dce-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="34dce-103">CorFlags 変換ツールを使用して、ポータブル実行可能 (PE) ファイル イメージのヘッダー内の CorFlags セクションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="34dce-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="34dce-104">このツールは、Visual Studio と共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="34dce-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="34dce-105">このツールを実行するには、Visual Studio 用開発者コマンド プロンプト (または Windows 7 の Visual Studio コマンド プロンプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="34dce-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="34dce-106">詳細については、「[コマンド プロンプト](developer-command-prompt-for-vs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34dce-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="34dce-107">コマンド プロンプトに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34dce-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34dce-108">構文</span><span class="sxs-lookup"><span data-stu-id="34dce-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="34dce-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34dce-109">Parameters</span></span>  
  
|<span data-ttu-id="34dce-110">必須パラメーター</span><span class="sxs-lookup"><span data-stu-id="34dce-110">Required parameter</span></span>|<span data-ttu-id="34dce-111">[説明]</span><span class="sxs-lookup"><span data-stu-id="34dce-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="34dce-112">CorFlags を設定するアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="34dce-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="34dce-113">オプション</span><span class="sxs-lookup"><span data-stu-id="34dce-113">Option</span></span>|<span data-ttu-id="34dce-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="34dce-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="34dce-115">32BITREQUIRED フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="34dce-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="34dce-116">32BITREQUIRED フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="34dce-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="34dce-117">32BITPREFERRED フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="34dce-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="34dce-118">アプリは、64 ビット プラットフォーム上でも 32 ビット プロセスとして実行します。</span><span class="sxs-lookup"><span data-stu-id="34dce-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="34dce-119">このフラグは、EXE ファイルでのみ設定します。</span><span class="sxs-lookup"><span data-stu-id="34dce-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="34dce-120">このフラグを DLL で設定した場合、64 ビット プロセスで DLL を読み込むことができず、<xref:System.BadImageFormatException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="34dce-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="34dce-121">このフラグを設定した EXE ファイルは、64 ビット プロセスで読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="34dce-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="34dce-122">.NET Framework 4.5 で新たに追加されました。</span><span class="sxs-lookup"><span data-stu-id="34dce-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="34dce-123">32BITPREFERRED フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="34dce-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="34dce-124">.NET Framework 4.5 で新たに追加されました。</span><span class="sxs-lookup"><span data-stu-id="34dce-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="34dce-125">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="34dce-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="34dce-126">厳密な名前が付けられているアセンブリであっても、強制的に更新します。</span><span class="sxs-lookup"><span data-stu-id="34dce-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="34dce-127">**重要:**  厳密な名前が付けられているアセンブリを更新する場合は、そのコードを実行する前に再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34dce-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="34dce-128">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="34dce-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="34dce-129">ILONLY フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="34dce-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="34dce-130">ILONLY フラグをクリアします。</span><span class="sxs-lookup"><span data-stu-id="34dce-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="34dce-131">Microsoft 著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="34dce-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="34dce-132">CLR ヘッダー バージョンを 2.0 に戻します。</span><span class="sxs-lookup"><span data-stu-id="34dce-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="34dce-133">CLR ヘッダー バージョンを 2.5 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="34dce-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="34dce-134">**注:**  アセンブリをネイティブに実行するには、CLR ヘッダー バージョン 2.5 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="34dce-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34dce-135">解説</span><span class="sxs-lookup"><span data-stu-id="34dce-135">Remarks</span></span>  
 <span data-ttu-id="34dce-136">オプションが何も指定されていない場合、CorFlags 変換ツールは指定されているアセンブリのフラグを表示します。</span><span class="sxs-lookup"><span data-stu-id="34dce-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dce-137">参照</span><span class="sxs-lookup"><span data-stu-id="34dce-137">See also</span></span>

- [<span data-ttu-id="34dce-138">ツール</span><span class="sxs-lookup"><span data-stu-id="34dce-138">Tools</span></span>](index.md)
- [<span data-ttu-id="34dce-139">64 ビット アプリケーション</span><span class="sxs-lookup"><span data-stu-id="34dce-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="34dce-140">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="34dce-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
