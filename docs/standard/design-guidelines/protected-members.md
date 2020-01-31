---
title: プロテクト メンバー
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 44d342662e1aaeb51f14470f354f2dadd9a6f18d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743651"
---
# <a name="protected-members"></a><span data-ttu-id="f8a3d-102">プロテクト メンバー</span><span class="sxs-lookup"><span data-stu-id="f8a3d-102">Protected Members</span></span>
<span data-ttu-id="f8a3d-103">保護されたメンバー自体が拡張機能を提供することはありませんが、より強力なサブクラス化によって、拡張性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="f8a3d-104">これらを使用すると、メインのパブリックインターフェイスを不必要に複雑にすることなく、高度なカスタマイズオプションを公開できます。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="f8a3d-105">フレームワークデザイナーは、保護されたメンバーに注意する必要があります。これは、"protected" という名前のセキュリティが誤った意味を持つ可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="f8a3d-106">だれでも、封印されていないクラスをサブクラス化し、保護されたメンバーにアクセスできるので、パブリックメンバーに使用される同じ防御的なコーディング方法がすべてプロテクトメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="f8a3d-107">高度なカスタマイズには、保護されたメンバーの使用を検討✔️。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-107">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="f8a3d-108">✔️は、セキュリティ、ドキュメント、互換性分析のために、封印されていないクラスのプロテクトメンバーをパブリックとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-108">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="f8a3d-109">だれでもクラスを継承し、保護されたメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f8a3d-109">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="f8a3d-110">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="f8a3d-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f8a3d-111">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="f8a3d-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a3d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8a3d-112">See also</span></span>

- [<span data-ttu-id="f8a3d-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f8a3d-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f8a3d-114">機能拡張のデザイン</span><span class="sxs-lookup"><span data-stu-id="f8a3d-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
