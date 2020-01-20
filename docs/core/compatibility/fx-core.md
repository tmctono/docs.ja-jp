---
title: 破壊的変更 - .NET Framework から .NET Core
description: .NET Framework から .NET Core への破壊的変更を一覧表示します。
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900121"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="611e7-103">.NET Framework から .NET Core への移行の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="611e7-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="611e7-104">.NET Framework から .NET Core にアプリを移行する場合、この記事の一覧にある破壊的変更による影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="611e7-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="611e7-105">破壊的変更は、カテゴリ別にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="611e7-105">Breaking changes are grouped by category.</span></span>

> [!NOTE]
> <span data-ttu-id="611e7-106">この記事は、.NET Framework と .NET Core の間の破壊的変更の完全な一覧ではありません。</span><span class="sxs-lookup"><span data-stu-id="611e7-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="611e7-107">最も重要な破壊的変更が認識されると、こちらに追加されます。</span><span class="sxs-lookup"><span data-stu-id="611e7-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="611e7-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="611e7-108">CoreFx</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a><span data-ttu-id="611e7-109">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="611e7-109">Windows Forms</span></span>

<span data-ttu-id="611e7-110">.NET Framework から .NET Core 3.0 以降に Windows Forms アプリを移行する際の破壊的変更については、[Windows フォームの破壊的変更 (.NET Framework から .NET Core)](../porting/winforms-breaking-changes.md) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="611e7-110">For information about breaking changes when you migrate a Windows Forms app from .NET Framework to .NET Core 3.0 or later, see [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="611e7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="611e7-111">See also</span></span>

- [<span data-ttu-id="611e7-112">.NET Core で常に例外をスローする API</span><span class="sxs-lookup"><span data-stu-id="611e7-112">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="611e7-113">.NET Core で使用できない .NET Framework テクノロジ</span><span class="sxs-lookup"><span data-stu-id="611e7-113">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
