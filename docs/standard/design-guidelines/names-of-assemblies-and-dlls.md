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
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709258"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="3c827-102">アセンブリと DLL の名前</span><span class="sxs-lookup"><span data-stu-id="3c827-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="3c827-103">アセンブリは、マネージコードプログラムの配置と id の単位です。</span><span class="sxs-lookup"><span data-stu-id="3c827-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="3c827-104">アセンブリは1つ以上のファイルにまたがることができますが、通常、アセンブリは1対1のを DLL とマップします。</span><span class="sxs-lookup"><span data-stu-id="3c827-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="3c827-105">したがって、このセクションでは DLL の名前付け規則についてのみ説明し、次にアセンブリの名前付け規則にマップできます。</span><span class="sxs-lookup"><span data-stu-id="3c827-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="3c827-106">**✓ DO** アセンブリ System.Data などの機能の大きなチャンクを提案する Dll の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c827-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="3c827-107">アセンブリ名と DLL 名は、名前空間名に対応する必要はありませんが、アセンブリに名前を付けるときは、名前空間名に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c827-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="3c827-108">経験則として、アセンブリに含まれる名前空間の共通のプレフィックスに基づいて DLL の名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c827-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="3c827-109">たとえば、`MyCompany.MyTechnology.FirstFeature` と `MyCompany.MyTechnology.SecondFeature`の2つの名前空間を持つアセンブリを `MyCompany.MyTechnology.dll`と呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3c827-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="3c827-110">**✓ CONSIDER** Dll を次のパターンに従って名前付け。</span><span class="sxs-lookup"><span data-stu-id="3c827-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="3c827-111">ここで、`<Component>` には1つ以上のドット区切り句が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c827-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="3c827-112">例:</span><span class="sxs-lookup"><span data-stu-id="3c827-112">For example:</span></span>  
  
 <span data-ttu-id="3c827-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="3c827-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="3c827-114">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="3c827-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3c827-115">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="3c827-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c827-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c827-116">See also</span></span>

- [<span data-ttu-id="3c827-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3c827-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3c827-118">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3c827-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
