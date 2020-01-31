---
title: アセンブリと DLL の名前
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744172"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="f20e2-102">アセンブリと DLL の名前</span><span class="sxs-lookup"><span data-stu-id="f20e2-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="f20e2-103">アセンブリは、マネージコードプログラムの配置と id の単位です。</span><span class="sxs-lookup"><span data-stu-id="f20e2-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="f20e2-104">アセンブリは1つ以上のファイルにまたがることができますが、通常、アセンブリは1対1のを DLL とマップします。</span><span class="sxs-lookup"><span data-stu-id="f20e2-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="f20e2-105">したがって、このセクションでは DLL の名前付け規則についてのみ説明し、次にアセンブリの名前付け規則にマップできます。</span><span class="sxs-lookup"><span data-stu-id="f20e2-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="f20e2-106">アセンブリ Dll の名前を選択して、システムデータなどの大量の機能を提案する✔️ます。</span><span class="sxs-lookup"><span data-stu-id="f20e2-106">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="f20e2-107">アセンブリ名と DLL 名は、名前空間名に対応する必要はありませんが、アセンブリに名前を付けるときは、名前空間名に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f20e2-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="f20e2-108">経験則として、アセンブリに含まれる名前空間の共通のプレフィックスに基づいて DLL の名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f20e2-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="f20e2-109">たとえば、`MyCompany.MyTechnology.FirstFeature` と `MyCompany.MyTechnology.SecondFeature`の2つの名前空間を持つアセンブリを `MyCompany.MyTechnology.dll`と呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f20e2-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="f20e2-110">✔️ Dll には、次のパターンに従って名前を付けることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f20e2-110">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="f20e2-111">ここで、`<Component>` には1つ以上のドット区切り句が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f20e2-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="f20e2-112">例:</span><span class="sxs-lookup"><span data-stu-id="f20e2-112">For example:</span></span>

 <span data-ttu-id="f20e2-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="f20e2-113">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="f20e2-114">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="f20e2-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f20e2-115">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="f20e2-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f20e2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f20e2-116">See also</span></span>

- [<span data-ttu-id="f20e2-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f20e2-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f20e2-118">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f20e2-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
