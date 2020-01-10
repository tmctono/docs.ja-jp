---
title: 名前付けガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: ad98c0f3b02bdc81e6348493b4e0a02f9cb20ed4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709193"
---
# <a name="naming-guidelines"></a><span data-ttu-id="5577c-102">名前付けガイドライン</span><span class="sxs-lookup"><span data-stu-id="5577c-102">Naming Guidelines</span></span>
<span data-ttu-id="5577c-103">フレームワーク開発で一貫した名前付け規則に従うことは、フレームワークの使いやすさへの主要な貢献となりえます。</span><span class="sxs-lookup"><span data-stu-id="5577c-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="5577c-104">これにより、広範囲に分散されたプロジェクトで多くの開発者が使用するフレームワークができます。</span><span class="sxs-lookup"><span data-stu-id="5577c-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="5577c-105">形式の一貫性以上に、フレームワーク要素の名前は簡単に理解でき、各要素の機能を伝えるものでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5577c-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="5577c-106">この章の目的は、開発者に即時に意味のある名前になる、一貫性のある名前付け規則のセットを提供することです。</span><span class="sxs-lookup"><span data-stu-id="5577c-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="5577c-107">これらの名前付け規約を一般的なコード開発ガイドラインとして採用すれば、より一貫した名前付けをコード全体で実現できますが、必須とされるのはパブリックに公開された API (public または protected な型やメンバー、および明示的に実装されたインターフェイス) への適用のみです。</span><span class="sxs-lookup"><span data-stu-id="5577c-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5577c-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5577c-108">In This Section</span></span>  
 [<span data-ttu-id="5577c-109">大文字の使用規則</span><span class="sxs-lookup"><span data-stu-id="5577c-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="5577c-110">一般的な名前付け規則</span><span class="sxs-lookup"><span data-stu-id="5577c-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="5577c-111">アセンブリと DLL の名前</span><span class="sxs-lookup"><span data-stu-id="5577c-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="5577c-112">名前空間の名前</span><span class="sxs-lookup"><span data-stu-id="5577c-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="5577c-113">クラス、構造体、およびインターフェイスの名前</span><span class="sxs-lookup"><span data-stu-id="5577c-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="5577c-114">型のメンバーの名前</span><span class="sxs-lookup"><span data-stu-id="5577c-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="5577c-115">パラメーターに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="5577c-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="5577c-116">リソースに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="5577c-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="5577c-117">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="5577c-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5577c-118">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="5577c-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5577c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5577c-119">See also</span></span>

- [<span data-ttu-id="5577c-120">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="5577c-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
