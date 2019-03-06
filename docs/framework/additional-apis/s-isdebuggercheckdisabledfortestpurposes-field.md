---
title: s_isDebuggerCheckDisabledForTestPurposes フィールド
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: b6490919163a7c4a618bf9a8d0e2aa145f60eda1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372309"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="164ed-102">s_isDebuggerCheckDisabledForTestPurposes フィールド</span><span class="sxs-lookup"><span data-stu-id="164ed-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="164ed-103">このプライベート フィールドで、`System.Windows.Diagnostics.VisualDiagnostics`クラスは、アクティブなデバッガー、内部のチェックを実行するかどうかを判断する Visual Studio によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="164ed-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="164ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="164ed-104">Syntax</span></span>

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> <span data-ttu-id="164ed-105">Api、`System.Windows.Diagnostics.VisualDiagnostics`クラスは、アプリケーションがデバッガーで実行されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="164ed-105">APIs in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="164ed-106">設定`s_isDebuggerCheckDisabledForTestPurposes`に`true`デバッガーの外部 Api にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="164ed-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>
>
> <span data-ttu-id="164ed-107">Microsoft はいかなる運用アプリケーションでこのフィールドの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="164ed-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="164ed-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="164ed-108">Requirements</span></span>

<span data-ttu-id="164ed-109">**名前空間:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="164ed-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="164ed-110">**アセンブリ:** PresentationCore (presentationcore.dll 内)</span><span class="sxs-lookup"><span data-stu-id="164ed-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="164ed-111">**.NET framework のバージョン:** 4.6 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="164ed-111">**.NET Framework versions:** Available since 4.6.</span></span>