---
title: <message> このエラーは、ファイル参照と '<assemblyname>' へのプロジェクト参照との混合によって生じた可能性があります。
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 263e30f992ef58b0053acb2fd749d0d9186ef6b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397260"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="75a91-102">\<message> このエラーは、ファイル参照と '\<assemblyname>' へのプロジェクト参照との混合によって生じた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75a91-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="75a91-103">\<message> このエラーは、ファイル参照とアセンブリ '\<assemblyname> へのプロジェクト参照との混合によって生じた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75a91-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="75a91-104">この場合、プロジェクト '\<projectname1>' の '\<assemblyfilename>' へのファイル参照を '\<projectname2>' へのプロジェクト参照で置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="75a91-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="75a91-105">プロジェクト内のコードが別のプロジェクトのメンバーにアクセスしていますが、ソリューションが Visual Basic コンパイラに参照の解決を許可するよう構成されていません。</span><span class="sxs-lookup"><span data-stu-id="75a91-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="75a91-106">別のアセンブリで定義されている型にアクセスするには、そのアセンブリへの参照を Visual Basic コンパイラが保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75a91-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="75a91-107">これは、プロジェクト間の循環参照にならない、単一であいまいさのない参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="75a91-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="75a91-108">**エラー ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="75a91-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="75a91-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="75a91-109">To correct this error</span></span>  
  
1. <span data-ttu-id="75a91-110">どのプロジェクトが、プロジェクトからの参照に最適なアセンブリを作成しているか特定します。</span><span class="sxs-lookup"><span data-stu-id="75a91-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="75a91-111">この判断には、ファイル アクセスの容易さや更新の頻度などの基準を使用できます。</span><span class="sxs-lookup"><span data-stu-id="75a91-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="75a91-112">プロジェクトのプロパティに、使用する型が定義されているアセンブリを含むプロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="75a91-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a91-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="75a91-113">See also</span></span>

- [<span data-ttu-id="75a91-114">プロジェクト内の参照の管理</span><span class="sxs-lookup"><span data-stu-id="75a91-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="75a91-115">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="75a91-115">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="75a91-116">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="75a91-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="75a91-117">壊れた参照のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="75a91-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
