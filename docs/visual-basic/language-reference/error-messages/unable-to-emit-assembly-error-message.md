---
title: 'アセンブリを作成できません : <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 5776755a57fbc2b0086b1c9b6cfbb2f2b7eb03fa
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197275"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="f1524-102">アセンブリを生成できません: \<エラーメッセージ ></span><span class="sxs-lookup"><span data-stu-id="f1524-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="f1524-103">Visual Basic コンパイラは、アセンブリリンカー (Al.exe、Alink とも呼ばれ*ます*) を呼び出してマニフェストを持つアセンブリを生成します。リンカーは、アセンブリの作成の出力段階でエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="f1524-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="f1524-104">**エラー ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="f1524-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f1524-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f1524-105">To correct this error</span></span>

1. <span data-ttu-id="f1524-106">引用符で囲まれたエラーメッセージを調べ、詳細な説明とアドバイスについては、「 [al.exe](../../../framework/tools/al-exe-assembly-linker.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1524-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="f1524-107">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)または[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)を使用して、手動でアセンブリに署名してみます。</span><span class="sxs-lookup"><span data-stu-id="f1524-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="f1524-108">エラーが続く場合は、状況に関する情報を収集し、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="f1524-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="f1524-109">アセンブリを手動で署名するには</span><span class="sxs-lookup"><span data-stu-id="f1524-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="f1524-110">[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md)) を使用して、公開キーと秘密キーのペアファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1524-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="f1524-111">このファイルの拡張子は *.snk*です。</span><span class="sxs-lookup"><span data-stu-id="f1524-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="f1524-112">エラーが発生している COM 参照をプロジェクトから削除します。</span><span class="sxs-lookup"><span data-stu-id="f1524-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="f1524-113">[Visual Studio の開発者コマンドプロンプト](../../../framework/tools/developer-command-prompt-for-vs.md)を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1524-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="f1524-114">Windows 10 では、タスクバーの検索ボックスに「**開発者コマンドプロンプト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f1524-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="f1524-115">次に、結果一覧から**開発者コマンドプロンプト [FOR VS 2017** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1524-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="f1524-116">ディレクトリを、アセンブリラッパーを配置するディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="f1524-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="f1524-117">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f1524-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="f1524-118">実際に入力するコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1524-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="f1524-119">パスまたはファイルにスペースが含まれている場合は、二重引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1524-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="f1524-120">Visual Studio で、先ほど作成したファイルに .NET アセンブリ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1524-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1524-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1524-121">See also</span></span>

- [<span data-ttu-id="f1524-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="f1524-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="f1524-123">Sn.exe (厳密名ツール)</span><span class="sxs-lookup"><span data-stu-id="f1524-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="f1524-124">方法: 公開キーと秘密キーのキー ペアを作成する</span><span class="sxs-lookup"><span data-stu-id="f1524-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="f1524-125">ご意見</span><span class="sxs-lookup"><span data-stu-id="f1524-125">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
