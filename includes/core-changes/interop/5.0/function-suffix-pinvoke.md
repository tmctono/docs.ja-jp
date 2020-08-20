---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062427"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="ec8ba-101">Windows 以外のプラットフォームでは A/W サフィックスのプローブは行われません</span><span class="sxs-lookup"><span data-stu-id="ec8ba-101">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="ec8ba-102">.NET ランタイムでは、Windows 以外のプラットフォームにおいて P/Invoke のプローブ中に関数エクスポート名に `A` または `W` サフィックスを追加しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-102">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ec8ba-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ec8ba-103">Version introduced</span></span>

<span data-ttu-id="ec8ba-104">5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="ec8ba-104">5.0 Preview 4</span></span>

#### <a name="change-description"></a><span data-ttu-id="ec8ba-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="ec8ba-105">Change description</span></span>

<span data-ttu-id="ec8ba-106">[Windows には、Windows コードページと Unicode バージョンに対応する `A` または `W` サフィックスを Windows SDK 関数名に追加するという ](/windows/win32/intl/conventions-for-function-prototypes) 規約があります。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-106">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="ec8ba-107">以前のバージョンの .NET では、CoreCLR と Mono の両方のランタイムによって、"*すべてのプラットフォームでの*" P/Invoke のエクスポートの検出時に、エクスポート名に `A` または `W` サフィックスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-107">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="ec8ba-108">.NET 5.0 以降のバージョンでは、"*Windows のみでの*" エクスポートの検出時に `A` または `W` サフィックスがエクスポート名に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-108">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="ec8ba-109">Unix プラットフォームでは、サフィックスは追加されません。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-109">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="ec8ba-110">Windows プラットフォーム上の両方のランタイムのセマンティクスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-110">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ec8ba-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="ec8ba-111">Reason for change</span></span>

<span data-ttu-id="ec8ba-112">この変更は、クロスプラットフォームのプローブを簡素化するために行われました。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-112">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="ec8ba-113">Windows 以外のプラットフォームにはこのセマンティックが含まれていないため、オーバーヘッドが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-113">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ec8ba-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="ec8ba-114">Recommended action</span></span>

<span data-ttu-id="ec8ba-115">変更を軽減するには、Windows 以外のプラットフォームに必要なサフィックスを手動で追加します。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-115">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="ec8ba-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ec8ba-116">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a><span data-ttu-id="ec8ba-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ec8ba-117">Category</span></span>

<span data-ttu-id="ec8ba-118">Interop</span><span class="sxs-lookup"><span data-stu-id="ec8ba-118">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ec8ba-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ec8ba-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
