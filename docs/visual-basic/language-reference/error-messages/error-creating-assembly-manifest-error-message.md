---
title: 'アセンブリ マニフェストを作成中にエラーが発生しました : <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 0f67b772bab3104c00510954d01b200aadfa9e8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803351"
---
# <a name="error-creating-assembly-manifest-error-message"></a><span data-ttu-id="45f88-102">アセンブリ マニフェストを作成中にエラー:\<エラー メッセージ ></span><span class="sxs-lookup"><span data-stu-id="45f88-102">Error creating assembly manifest: \<error message></span></span>
<span data-ttu-id="45f88-103">Visual Basic コンパイラでは、マニフェストを持つアセンブリを生成するには、アセンブリ リンカー (Al.exe、Alink とも呼ばれます) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45f88-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="45f88-104">リンカーが、アセンブリの生成前の段階でのエラーを報告しています。</span><span class="sxs-lookup"><span data-stu-id="45f88-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="45f88-105">指定したキー ファイルまたはキー コンテナーに原因がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="45f88-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="45f88-106">アセンブリに完全署名するには、公開キーと秘密キーに関する情報を含む有効なキー ファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45f88-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="45f88-107">アセンブリに遅延署名するには、**[遅延署名のみ]** チェック ボックスをオンにし、公開キー情報を含む有効なキー ファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45f88-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="45f88-108">アセンブリに遅延署名する場合、秘密キーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="45f88-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="45f88-109">詳細については、「[方法 :厳密な名前でアセンブリに署名する](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45f88-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="45f88-110">**エラー ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="45f88-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45f88-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="45f88-111">To correct this error</span></span>  
  
1. <span data-ttu-id="45f88-112">引用符で囲まれたエラー メッセージを確認し、トピックを参照してください。 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)します。</span><span class="sxs-lookup"><span data-stu-id="45f88-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="45f88-113">エラー AL1019 詳細な説明とアドバイス</span><span class="sxs-lookup"><span data-stu-id="45f88-113">for error AL1019 further explanation and advice</span></span>  
  
2. <span data-ttu-id="45f88-114">エラーが続く場合は、状況に関する情報を収集し、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="45f88-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f88-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="45f88-115">See also</span></span>

- [<span data-ttu-id="45f88-116">方法: 厳密な名前でアセンブリに署名する</span><span class="sxs-lookup"><span data-stu-id="45f88-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- <span data-ttu-id="45f88-117">[[署名] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/signing-page-project-designer)</span><span class="sxs-lookup"><span data-stu-id="45f88-117">[Signing Page, Project Designer](/visualstudio/ide/reference/signing-page-project-designer)</span></span>
- [<span data-ttu-id="45f88-118">Al.exe</span><span class="sxs-lookup"><span data-stu-id="45f88-118">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="45f88-119">ご意見</span><span class="sxs-lookup"><span data-stu-id="45f88-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
