---
title: 'アセンブリを作成できません : <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936280"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="6f350-102">アセンブリを作成できません:\<エラー メッセージ ></span><span class="sxs-lookup"><span data-stu-id="6f350-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="6f350-103">Visual Basic コンパイラはアセンブリ リンカーを呼び出す (*Al.exe*Alink とも呼ばれます)、マニフェストと、リンカーでアセンブリを生成する出力段階で、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="6f350-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="6f350-104">**エラー ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="6f350-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6f350-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6f350-105">To correct this error</span></span>

1. <span data-ttu-id="6f350-106">引用符で囲まれたエラー メッセージを確認し、トピックを参照してください。 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)のより詳細な説明とアドバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="6f350-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="6f350-107">アセンブリを手動で署名を使用して再試行してください、 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)または[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f350-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="6f350-108">エラーが続く場合は、状況に関する情報を収集し、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="6f350-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="6f350-109">アセンブリを手動で署名するには</span><span class="sxs-lookup"><span data-stu-id="6f350-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="6f350-110">使用して、 [Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)) 公開/秘密キー ペア ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f350-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="6f350-111">このファイルは、 *.snk*拡張機能。</span><span class="sxs-lookup"><span data-stu-id="6f350-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="6f350-112">エラーが発生している COM 参照をプロジェクトから削除します。</span><span class="sxs-lookup"><span data-stu-id="6f350-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="6f350-113">開く、 [Visual Studio 用開発者コマンド プロンプト](../../../framework/tools/developer-command-prompt-for-vs.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f350-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="6f350-114">Windows 10 では、次のように入力します。**開発者コマンド プロンプト**の検索ボックスに、タスク バーにします。</span><span class="sxs-lookup"><span data-stu-id="6f350-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="6f350-115">次に、選択**開発者コマンド プロンプト for VS 2017**結果リストから。</span><span class="sxs-lookup"><span data-stu-id="6f350-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="6f350-116">アセンブリ ラッパーを格納するディレクトリにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="6f350-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="6f350-117">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f350-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="6f350-118">実際のコマンドを入力する可能性がありますの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6f350-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="6f350-119">パスまたはファイルにスペースが含まれている場合は、二重引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f350-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="6f350-120">Visual Studio で作成したファイルへの参照を .NET アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="6f350-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f350-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f350-121">See also</span></span>

- [<span data-ttu-id="6f350-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="6f350-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="6f350-123">Sn.exe (厳密名ツール)</span><span class="sxs-lookup"><span data-stu-id="6f350-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="6f350-124">方法: 公開キーと秘密キーのキー ペアを作成する</span><span class="sxs-lookup"><span data-stu-id="6f350-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="6f350-125">ご意見</span><span class="sxs-lookup"><span data-stu-id="6f350-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)