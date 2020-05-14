---
title: 型 '<typename>' が定義されていません。
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 1f66b86a61fb0344a449bf0aa46b7655813c7c30
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664254"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="d8204-102">型 '\<typename>' が定義されていません</span><span class="sxs-lookup"><span data-stu-id="d8204-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="d8204-103">ステートメントで、定義されていない型の参照が行われました。</span><span class="sxs-lookup"><span data-stu-id="d8204-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="d8204-104">`Enum`、`Structure`、`Class`、`Interface` などの宣言ステートメントで型を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8204-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="d8204-105">**エラー ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="d8204-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8204-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d8204-106">To correct this error</span></span>  
  
- <span data-ttu-id="d8204-107">型定義とその参照の両方で同じスペルが使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8204-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="d8204-108">参照から型定義にアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8204-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="d8204-109">たとえば、型が別のモジュールにあり、`Private` と宣言されている場合は、型定義を参照元のモジュールに移動するか、それを `Public` と宣言します。</span><span class="sxs-lookup"><span data-stu-id="d8204-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="d8204-110">型の名前空間がプロジェクト内で再定義されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8204-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="d8204-111">その場合は、`Global` キーワードを使用して、型名を完全修飾します。</span><span class="sxs-lookup"><span data-stu-id="d8204-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="d8204-112">たとえば、プロジェクトで `System` という名前の名前空間を定義している場合、`Global` キーワード: `Global.System.Object` で完全修飾していない限り、<xref:System.Object?displayProperty=nameWithType> 型にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d8204-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="d8204-113">型が定義されていても、それが定義されているオブジェクト ライブラリまたはタイプ ライブラリが Visual Basic に登録されていない場合は、 **[プロジェクト]** メニューの **[参照の追加]** クリックし、該当するオブジェクト ライブラリまたはタイプ ライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8204-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="d8204-114">型が、対象の .NET Framework プロファイルの一部であるアセンブリに含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8204-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="d8204-115">詳細については、「[.NET Framework を対象とするエラーのトラブルシューティング](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8204-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8204-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8204-116">See also</span></span>

- [<span data-ttu-id="d8204-117">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="d8204-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d8204-118">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="d8204-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="d8204-119">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="d8204-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="d8204-120">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="d8204-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="d8204-121">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="d8204-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="d8204-122">プロジェクト内の参照の管理</span><span class="sxs-lookup"><span data-stu-id="d8204-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
