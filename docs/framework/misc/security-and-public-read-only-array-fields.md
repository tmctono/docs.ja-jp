---
title: セキュリティとパブリックの読み取り専用配列フィールド
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910738"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="0c73e-102">セキュリティとパブリックの読み取り専用配列フィールド</span><span class="sxs-lookup"><span data-stu-id="0c73e-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="0c73e-103">読み取り専用のパブリック配列フィールドを変更できるため、マネージライブラリから読み取り専用パブリック配列フィールドを使用して、アプリケーションの境界動作またはセキュリティを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="0c73e-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c73e-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c73e-104">Remarks</span></span>  
 <span data-ttu-id="0c73e-105">一部の .NET framework クラスには、プラットフォーム固有の境界パラメーターを含む読み取り専用のパブリックフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c73e-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="0c73e-106">たとえば<xref:System.IO.Path.InvalidPathChars> 、フィールドは、ファイルパス文字列で許可されていない文字を記述する配列です。</span><span class="sxs-lookup"><span data-stu-id="0c73e-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="0c73e-107">.NET Framework 全体に同様の多くのフィールドが存在します。</span><span class="sxs-lookup"><span data-stu-id="0c73e-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="0c73e-108">のような<xref:System.IO.Path.InvalidPathChars>パブリック読み取り専用フィールドの値は、コードまたはコードのアプリケーションドメインを共有するコードによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c73e-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="0c73e-109">アプリケーションの境界動作を定義するには、このような読み取り専用パブリック配列フィールドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0c73e-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="0c73e-110">そうすると、悪意のあるコードが境界の定義を変更し、予期しない方法でコードを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0c73e-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="0c73e-111">.NET Framework のバージョン2.0 以降では、パブリック配列フィールドを使用する代わりに、新しい配列を返すメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c73e-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="0c73e-112">たとえば、 <xref:System.IO.Path.InvalidPathChars>フィールドを使用する代わりに、 <xref:System.IO.Path.GetInvalidPathChars%2A>メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c73e-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="0c73e-113">.NET Framework 型では、内部的に境界の種類を定義するためにパブリックフィールドが使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0c73e-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="0c73e-114">代わりに、.NET Framework は個別のプライベートフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c73e-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="0c73e-115">これらのパブリックフィールドの値を変更しても、.NET Framework 型の動作は変更されません。</span><span class="sxs-lookup"><span data-stu-id="0c73e-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c73e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c73e-116">See also</span></span>

- [<span data-ttu-id="0c73e-117">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="0c73e-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
