---
title: 型 '<typename1>' の値を '<typename2>' に変換できません。
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766806"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="1debd-102">型の値 '\<typename1 >' に変換できません'\<typename2 >'。</span><span class="sxs-lookup"><span data-stu-id="1debd-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="1debd-103">型の値 '\<typename1 >' に変換できません。'\<typename2 >'。</span><span class="sxs-lookup"><span data-stu-id="1debd-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="1debd-104">型の不一致は、ファイル参照とアセンブリへの参照をプロジェクトの混合によって生じた可能性があります '\<assemblyname >'。</span><span class="sxs-lookup"><span data-stu-id="1debd-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="1debd-105">ファイル参照を置き換えてください '\<filepath >' プロジェクトで'\<projectname1 >' への参照をプロジェクトに '\<projectname2 >'。</span><span class="sxs-lookup"><span data-stu-id="1debd-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="1debd-106">プロジェクトがプロジェクト参照とファイル参照の両方を使用する場合、コンパイラは別に 1 つの型を変換できることを保証できません。</span><span class="sxs-lookup"><span data-stu-id="1debd-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="1debd-107">次の擬似コードは、このエラーを生成できる状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="1debd-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="1debd-108">プロジェクト`P1`、間接的なプロジェクト参照をプロジェクトを通じて行います`P2`プロジェクトに`P3`へのファイルを直接参照も`P3`します。</span><span class="sxs-lookup"><span data-stu-id="1debd-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="1debd-109">宣言`commonObject`ファイル参照を使用して`P3`への呼び出し中に`P2.getCommonClass`へのプロジェクト参照を使用して`P3`します。</span><span class="sxs-lookup"><span data-stu-id="1debd-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="1debd-110">この状況で問題は、ファイル参照がファイルのパスと出力ファイルの名前を指定する`P3`(通常 p3.dll) プロジェクトの参照が、ソース プロジェクトを識別中に (`P3`) プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="1debd-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="1debd-111">このため、コンパイラは保証できませんが、型`P3.commonClass`2 つの異なる参照を使用して、同じソース コードに由来します。</span><span class="sxs-lookup"><span data-stu-id="1debd-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="1debd-112">通常このような状況が発生するプロジェクト参照とファイル参照が混在します。</span><span class="sxs-lookup"><span data-stu-id="1debd-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="1debd-113">上の図で、問題がない場合に発生する`P1`への参照を直接プロジェクトに加えられた`P3`ファイル参照の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="1debd-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="1debd-114">**エラー ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="1debd-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1debd-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1debd-115">To correct this error</span></span>  
  
- <span data-ttu-id="1debd-116">ファイル参照をプロジェクト参照を変更します。</span><span class="sxs-lookup"><span data-stu-id="1debd-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1debd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1debd-117">See also</span></span>

- [<span data-ttu-id="1debd-118">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="1debd-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="1debd-119">プロジェクト内の参照の管理</span><span class="sxs-lookup"><span data-stu-id="1debd-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
