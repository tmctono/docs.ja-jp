---
title: .NET での COM 相互運用
description: .NET で COM ライブラリを相互運用する方法について説明します。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 07/11/2019
ms.openlocfilehash: 03ede2fc95f4114a4d80423bd7de2e46012a2431
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631426"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="5287d-103">.NET での COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="5287d-103">COM Interop in .NET</span></span>

<span data-ttu-id="5287d-104">コンポーネント オブジェクト モデル (COM) では、オブジェクトがその機能を他のコンポーネントに公開し、Windows プラットフォームのアプリケーションをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="5287d-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="5287d-105">ユーザーが既存のコード ベースを使用して相互運用できるように支援するために、.NET Framework は、COM ライブラリとの相互運用に向けて常に強力なサポートを行っています。</span><span class="sxs-lookup"><span data-stu-id="5287d-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="5287d-106">.NET Core 3.0 では、このサポートの大部分が、Windows の .NET Core に追加されました。</span><span class="sxs-lookup"><span data-stu-id="5287d-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="5287d-107">このドキュメントでは、共通の COM 相互運用テクノロジのしくみと、既存の COM ライブラリとの相互運用に向けたその利用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5287d-107">The documentation here will explain how the common COM interop techonologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="5287d-108">COM ラッパー</span><span class="sxs-lookup"><span data-stu-id="5287d-108">COM Wrappers)</span></span>](./com-wrappers.md)
- [<span data-ttu-id="5287d-109">COM 呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="5287d-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="5287d-110">ランタイム呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="5287d-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="5287d-111">COM 相互運用のための .NET 型の要件</span><span class="sxs-lookup"><span data-stu-id="5287d-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
