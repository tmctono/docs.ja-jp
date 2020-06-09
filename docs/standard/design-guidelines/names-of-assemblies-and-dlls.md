---
title: アセンブリと DLL の名前
description: アセンブリとダイナミックリンクライブラリ (Dll) の名前付けのガイドラインについて説明します。 アセンブリは1つ以上のファイルにまたがることができますが、通常は1対1のファイルを DLL とマップします。
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: de7ce3ee774d4598521d7156d0d660c3fe30154c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594479"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="7ef14-104">アセンブリと DLL の名前</span><span class="sxs-lookup"><span data-stu-id="7ef14-104">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="7ef14-105">アセンブリは、マネージコードプログラムの配置と id の単位です。</span><span class="sxs-lookup"><span data-stu-id="7ef14-105">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="7ef14-106">アセンブリは1つ以上のファイルにまたがることができますが、通常、アセンブリは1対1のを DLL とマップします。</span><span class="sxs-lookup"><span data-stu-id="7ef14-106">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="7ef14-107">したがって、このセクションでは DLL の名前付け規則についてのみ説明し、次にアセンブリの名前付け規則にマップできます。</span><span class="sxs-lookup"><span data-stu-id="7ef14-107">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="7ef14-108">アセンブリ Dll の名前を選択して、システムデータなどの大量の機能を提案する✔️ます。</span><span class="sxs-lookup"><span data-stu-id="7ef14-108">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="7ef14-109">アセンブリ名と DLL 名は、名前空間名に対応する必要はありませんが、アセンブリに名前を付けるときは、名前空間名に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ef14-109">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="7ef14-110">経験則として、アセンブリに含まれる名前空間の共通のプレフィックスに基づいて DLL の名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ef14-110">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="7ef14-111">たとえば、との2つの名前空間を持つアセンブリを `MyCompany.MyTechnology.FirstFeature` `MyCompany.MyTechnology.SecondFeature` 呼び出すことができ `MyCompany.MyTechnology.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="7ef14-111">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="7ef14-112">✔️ Dll には、次のパターンに従って名前を付けることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7ef14-112">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="7ef14-113">に `<Component>` は1つ以上のドット区切り句が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ef14-113">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="7ef14-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7ef14-114">For example:</span></span>

 <span data-ttu-id="7ef14-115">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="7ef14-115">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="7ef14-116">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="7ef14-116">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="7ef14-117">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="7ef14-117">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="7ef14-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ef14-118">See also</span></span>

- [<span data-ttu-id="7ef14-119">フレームワークデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="7ef14-119">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="7ef14-120">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="7ef14-120">Naming Guidelines</span></span>](naming-guidelines.md)
