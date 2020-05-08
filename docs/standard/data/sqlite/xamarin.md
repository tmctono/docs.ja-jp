---
title: Xamarin の制限事項
ms.date: 12/13/2019
description: Xamarin の使用時に経験する制限事項について説明します。
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450406"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="ba101-103">Xamarin の制限事項</span><span class="sxs-lookup"><span data-stu-id="ba101-103">Xamarin limitations</span></span>

<span data-ttu-id="ba101-104">Microsoft.Data.Sqlite は .NET Standard 2.0 を対象とし、Xamarin でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ba101-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="ba101-105">次の表は、既定の SQLitePCLRaw バンドルによってネイティブ SQLite バイナリが提供されるプラットフォームを示しています。</span><span class="sxs-lookup"><span data-stu-id="ba101-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="ba101-106">別のバンドルを使用する場合、または独自のネイティブ SQLite バイナリを用意する場合の詳細については、「[カスタム SQLite のバージョン](custom-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba101-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="ba101-107">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ba101-107">Platform</span></span> | <span data-ttu-id="ba101-108">SQLite バイナリ</span><span class="sxs-lookup"><span data-stu-id="ba101-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="ba101-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="ba101-109">**Xamarin.Android**</span></span> | <span data-ttu-id="ba101-110">—</span><span class="sxs-lookup"><span data-stu-id="ba101-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="ba101-111">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="ba101-112">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="ba101-113">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="ba101-114">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-114">✔</span></span> |
| <span data-ttu-id="ba101-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="ba101-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="ba101-116">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-116">✔</span></span> |
| <span data-ttu-id="ba101-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="ba101-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="ba101-118">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-118">✔</span></span> |
| <span data-ttu-id="ba101-119">**Xamarin.TVOS**</span><span class="sxs-lookup"><span data-stu-id="ba101-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="ba101-120">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-120">✔</span></span> |
| <span data-ttu-id="ba101-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="ba101-121">**UWP**</span></span> | <span data-ttu-id="ba101-122">—</span><span class="sxs-lookup"><span data-stu-id="ba101-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="ba101-123">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="ba101-124">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="ba101-125">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="ba101-126">✔</span><span class="sxs-lookup"><span data-stu-id="ba101-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="ba101-127">iOS</span><span class="sxs-lookup"><span data-stu-id="ba101-127">iOS</span></span>

<span data-ttu-id="ba101-128">Microsoft.Data.Sqlite では、SQLitePCLRaw バンドルの初期化が自動的に試みられます。</span><span class="sxs-lookup"><span data-stu-id="ba101-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="ba101-129">しかし、Xamarin.iOS の事前 (AOT) コンパイルに制限があるため、この試みは失敗し、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba101-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="ba101-130">`SQLitePCL.raw.SetProvider()` を呼び出す必要があります。(You need to call SQLitePCL.raw.SetProvider().)</span><span class="sxs-lookup"><span data-stu-id="ba101-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="ba101-131">バンドル パッケージを使用している場合、これは `SQLitePCL.Batteries.Init()` を呼び出すことによって行われます。(If you're using a bundle package, this is done by calling SQLitePCL.Batteries.Init().)</span><span class="sxs-lookup"><span data-stu-id="ba101-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="ba101-132">バンドルを初期化するには、Microsoft. Data. Sqlite を使用する前に次のコード行をアプリに追加してください。</span><span class="sxs-lookup"><span data-stu-id="ba101-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="ba101-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba101-133">See also</span></span>

* [<span data-ttu-id="ba101-134">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="ba101-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="ba101-135">カスタム SQLite のバージョン</span><span class="sxs-lookup"><span data-stu-id="ba101-135">Custom SQLite versions</span></span>](custom-versions.md)
